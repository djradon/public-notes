---
id: 8rajl5vlvylqjny5hgr1t5l
title: Modelling Time within a Strongly Typed Database
desc: ''
updated: 1694796383525
created: 1694796319022
---

- #url https://blog.vaticle.com/modelling-time-within-a-strongly-typed-database-55ba91ecad62

Published in

Vaticle
·
9 min read
·
Jun 21, 2021

--

Time is the indefinite continued progress of existence and events that occur in an apparently irreversible succession from the past, through the present, into the future¹. The dynamics of systems operating over time are responsible for much of the apparent nonlinearity we observe, causal sequences travel forward in time, and the full impact of time is thereby rather interesting.
Background to Temporal Modelling

In the data context, many conceptual facets of time can be hard to capture, particularly in an RDBMS. Depending on the application, various complexities can arise in modelling time-based data, including:

    Storage and Indexing: How to store time data fields so they can be accessed quickly
    Division and Aggregation: The smallest sensible time increment, and aggregation methods
    Multiple Timelines: Dealing with changing data
    Slowly Changing Dimensions: Classifying responses to temporal data changes
    Temporally Variable Schema and Data: Capturing schema and data changes
    Mining Temporal Relations: Methods of relating times to other times (e.g. before, after etc.)

These basics must be mastered before moving onto dynamic systems and causality. But they are not small issues, as entire databases have been devised and market shares carved out around the idea of being good at Problem 1 and 2 generally (e.g. MapR, TimeDB), or for specific use cases such as IoT.

Much time and effort have been put into Problems 3, 4 and 5 particularly with RDBMS and Dimensional Warehouses (e.g. DataVault), and even SQL extension recommendations. OWL-Time is the dominant solution for Problem 6 and has notorious ambiguity problems.

Most graph types require everything to be an entity (e.g. property graph), when in fact in the real world, entities are few, and everything else is attributes connected by relations. TypeDB has a unique data model that makes temporal modelling powerful and simple.
Temporal Variables — A Common Application

A key challenge in databases is to support temporal variables that are only valid for a certain period of time, and can be safely updated while preserving the original value. This requires (1) storage and indexing of timestamped data and, (3) multiple timelines.
Multiple timelines for one value²

In order to flesh out the example, the scenario from Timely Concerns in Data Models² will be used.

Consider the diagram below, which shows a typical property graph model (i.e. nodes are mini-tables); the question is how I would change this in order to record all reads/writes and changing values (i.e. have read and write timelines on everything)? There are many ways we could model this system in TypeQL. For example, we could take the property graph view, as in the image and make everything entities.
Example Data Model²

As a strongly typed database, TypeDB provides a particularly strong platform for temporal modelling. Consider the image below.
TypeQL — (Note: A Thing is an Entity, an Attribute or a Relation)

The diagram demonstrates that in TypeQL relations can do everything entities can do, plus link roles. Further, attributes can own other attributes and play roles in relations. Not shown is the fact that attributes are unique values, which is then related to each instance of use. Finally, I will follow the lead of Haikal (CEO, Vaticle) in his insight that local increases in intricacy lead to lower overall complexity. Thus, we will start from the inside out.
Step 1: An Expanded definition of time

Time and date are usually recorded with a timestamp, a multi-scale record of the number of periods since a reference event. Each scale represents an integer multiple of a specific time period (years, months, days, hours, mins, secs, msec) and the entire date and time combination is a string of these period scales. Indexing a single year needs to take account of ~3 x 10¹⁰ unique variations.
Unique Values to Index = 3.1 x 10¹⁰ /year

TypeQL has unique capabilities that enable us to take advantage of this problem since attributes can own other attributes and have unique values. These capabilities enable us to form a composite index on time (a set of buckets using integers), taking the indexing requirement for a single year of microseconds down to 1,188 unique values.
Unique Values to Index = 1,188 /year

In a future version of TypeQL, this concept of canonical composite attributes with enums for the units and conversion functions is expected to be implemented to create a powerful system for units. But for the moment, it is only useful in indexing records. Below, the TypeQL schema for UTC is shown.

#####################################
# TypeQL Temporal Lists Model
# - capturing the read/writes and changing values
#########################################define# 1.A. Setup UTC time fast-indexing system   year sub attribute, value long;
   month sub attribute, value long;
   day sub attribute, value long;
   hour sub attribute, value long;
   mins sub attribute, value long;
   secs sub attribute, value long;
   msecs sub attribute, value long;   UTC sub attribute, 
      value date,
      owns year,
      owns month,
      owns day,
      owns hour,
      owns mins,
      owns secs,
      owns msecs;

Since we are building a business system, it is convenient to expand that definition to bring in the finance temporal categories.

# 1.B. Setup finance time   week sub attribute, value long;
   quarter sub attribute, value long;
   fin_quarter sub attribute, value long;
   half sub attribute, value long;
   fin_half sub attribute, value long;
   fin_year sub attribute, value long;   finance_time sub UTC,
      owns week,
      owns quarter,
      owns fin_quarter,
      owns half,
      owns fin_half,
      owns fin_year;

For the moment, these are standalone data objects and don’t play any roles. They perhaps could have been marked as abstract. To use them, it would be convenient to input all of the indexes as a batch operation and then match them into the insert of a specific date-time-stamp.
Step 2: Setup a Temporal List

In a business system, much of the data we deal with, like addresses, dependent, project_work, and dept_managerare not actually independent things. Instead, they have a temporal nature. During periods of time, there are various facts that are true and periods when these facts change. Taking advantage of TypeQL’s polymorphic nature, we define a generic temporal list that contains any number of items and then subclass it for our four temporal data elements.

#2. Setup Temporal List, with SubTypes

   temporal_list sub relation,
      owns intIndex, # not a key
      owns op_type, # enum of read/write
      owns current, # boolean value, set by rules
      relates owner, # entity owner, employee this data is for 
      relates item, # the data fragment
      relates user_id, # accessor user id, not an employee number 
      relates created; # finance_time the data was created

   address sub temporal_list;
   dependant sub temporal_list;
   project_work sub temporal_list;
   dept_manager sub temporal_list;`

Step 3: Setup Temporal List Data

This temporal list structure turns out to be a very handy way of storing objects and accessing them. The aim is to input all list elements with current =falseand then have rules to determine which is current. At present, the list is a bit of hard work, as one must pull the current record and use its index + 1 for the new insert. However, this is expected to get much easier once calculation comes in, as one can automate the index. The data for the temporal list is defined below:

#3. Setup the Data for the Temporal List

   street sub attribute, 
      value string, 
      plays temporal_list:item;
   city sub attribute, 
      value string, 
      plays temporal_list:item;
   postcode sub attribute, 
      value string, 
      plays temporal_list:item;
   state sub attribute, 
      value string, 
      plays temporal_list:item;
   dep_id sub attribute, 
      value string, 
      plays temporal_list:item;
   dep_name sub attribute, 
      value string, 
      plays temporal_list:item;
   dep_gender sub attribute, 
      value string, 
      plays temporal_list:item;
   dep_birthdate sub attribute, 
      value date, 
      plays temporal_list:item;
   proj_id sub attribute, 
      value string, 
      plays temporal_list:item;
   proj_name sub attribute, 
      value string, 
      plays temporal_list:item;
   dept_id sub attribute, 
      value string, 
      plays temporal_list:item;
   dept_name sub attribute, 
      value string, 
      plays temporal_list:item;

Step 4: Setup local time definition

The local-time to use for this database can be sub-classed from the previously defined time structures:

#4. Setup the local time definition

   loc_time sub finance_time, 
      plays temporal_list:created;

Step 5: Setup the Person Entity

Finally, we set up the only entity in this sub-model, which is a person, the employee who “owns” the data records (i.e. the employee whose data is being accessed), as shown below:

# 5. finally setup the employee definition to own the data

   employee_name sub attribute, value string;
   employee_id sub attribute, value string;
   social_security sub attribute, value string;
   birthdate sub attribute, value date;
   gender sub attribute, value string;

   employee sub entity,
      owns employee_id,
      owns employee_name,
      owns social_security,
      owns birthdate,
      owns gender,
      plays temporal_list:owner;

Step 6: Insert a temporal record

As discussed previously, assuming we input the time first and the accessor user id is the email address, then inserting a temporal record amounts to:

# 6. insert a temporal record

match
   $emp isa employee, has employee_id '#%$@-@#%';
   $uid isa userID, $uid 'user@example.com';
   $tim isa loctime; $tim '2018-09-17T18:54:16.717Z';
insert
   $str isa street; $str '92 Campbell Parade';
   $cit isa city; $cit 'Bondi Beach';
   $pos isa postcode; $pos '2026';
   $sta isa state; $sta 'NSW'
   $adr (owner:$emp, user_id:$uid, item:$str, item: $cit, 
      item:$pos, item:$sta, created:$tim) isa address,
      has intIndex 0,
      has type 'write_op',
      has current false;

Step 7: Match a temporal record

Assuming the rule to determine the current is in play, then querying the current is easy, as shown below, although one should also write back a new read record.

# 7. get the value from a temporal record

match
   $emp isa employee, owns employee_id '#%$@-@#%';
      (owner:$emp, item:$it) isa address, 
       has op_type 'write_op',
       has current true;

Discussion

As a strongly typed database, TypeDB’s unique data model makes the representation of temporal records a snap. Firstly, the unique nature of attributes mean a composite index can index any time in a 10-year span within <1,200 unique values. This can be extended into making an easy method to reference all values within a given financial period, such as a particular quarter, or month etc.

    Most graph types require everything to be an entity (e.g. property graph), when in fact in the real world, entities are few, and everything else is attributes connected by relations. TypeDB has a unique data model that makes temporal modelling powerful and simple.

The interesting thing about the TypeQL query language is that it can model almost any other data storage approach, and I like lists because they are easy. I personally use lists a lot, as well as dicts, for storage in TypeQL, and there are two circumstances:

    I insert an entire list at once, for example, a session in a log with events, and in this case, I use a dummy “stop” value at the end of each list, so it is easy to get.
    Insert items in a list incrementally, as shown above; in this case, I would match out the index of the current record, add 1 to it (in the client) and insert it in the new list item.

Once calculations are in, this becomes a lot easier, and it can be accomplished in a single match/insert. We could hope to see calculations and canonical composite attributes late this year.

This article is an excerpt from a post and subsequent discussion on Vaticle Discord. If you enjoyed this piece and would like to contribute to the active discussions around modelling time in TypeDB, head to the Vaticle Community discord. Thanks to Daniel for encouraging me to post this thread!!
Bibliography

[1] Wikipedia: Time
https://en.wikipedia.org/wiki/Time

[2] Thomas Frisendal — Timely Concerns in Data Models, June 10, 2019
https://www.dataversity.net/timely-concerns-in-data-models/
Typedb
Data Modeling
Type Systems
Database Development
Database

--
Modeller
Vaticle
Written by Modeller
52 Followers
·Writer for 

Vaticle

A modeller
Follow
More from Modeller and Vaticle
Accelerating drug discovery with applied knowledge engineering and TypeDB
James Whiteside

James Whiteside

in

Vaticle
Accelerating drug discovery with applied knowledge engineering and TypeDB
Knowledge discovery involves a tremendous amount of heterogeneous data, which is difficult to integrate due to its complex nature and rich…
11 min read·Jul 18

--

1
The need for subtyping and polymorphism in databases
Shane K Johnson

Shane K Johnson

in

Vaticle
The need for subtyping and polymorphism in databases
A simpler, safer and more powerful way to define and query expressive data models
17 min read·Aug 15

--
The age of AI is upon us — where are the smart databases?
Shane K Johnson

Shane K Johnson

in

Vaticle
The age of AI is upon us — where are the smart databases?
AI is arriving, and it’s coming in hot.
5 min read·Jul 18

--
Inheritance and polymorphism: where the cracks in SQL begin to show
James Whiteside

James Whiteside

in

Vaticle
Inheritance and polymorphism: where the cracks in SQL begin to show
Polymorphism can be one of the most challenging things to model in a database. Not only do you want your database to be performant, you…
13 min read·Jul 12

--

2
See all from Modeller
See all from Vaticle
Recommended from Medium
Why You Need a Knowledge Graph, And How to Build It
Stan Pugsley

Stan Pugsley

in

Towards Data Science
Why You Need a Knowledge Graph, And How to Build It
A Guide to Migrating from a Relational Database to a Graph Database
7 min read·Aug 9

--

9
Graphs and Graph Applications
Lei Wang

Lei Wang

in

graphscope
Graphs and Graph Applications
In this post, we will introduce basic concepts of graphs, and some typical applications of graph algorithms.
7 min read·May 22

--
Lists
Databricks role-based and specialty certification line-up.
New_Reading_List
174 stories·77 saves
Intro — Sports Intelligence @ DraftKings
Robin Mohseni

Robin Mohseni

in

DraftKings Engineering
Intro — Sports Intelligence @ DraftKings
Co-written by Ian Dorward, Prashant Singh and Robin Mohseni
7 min read·Jul 14

--
5 Situational Design Patterns for Data Modelling
Martin ter Haak

Martin ter Haak
5 Situational Design Patterns for Data Modelling
Level up on data modelling with these situational patterns in part 2 of my series on data modelling
17 min read·Mar 12

--

1
Neo4j: Unraveling Complex Relationships in Data with Graph Databases
Roshmita Dey

Roshmita Dey
Neo4j: Unraveling Complex Relationships in Data with Graph Databases
In the ever-evolving landscape of data management, traditional relational databases have long been the cornerstone of structured…
4 min read·Aug 10

--
