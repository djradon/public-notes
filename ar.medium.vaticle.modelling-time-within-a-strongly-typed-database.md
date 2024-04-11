---
id: x2tvx8dxd0gwfgkoweegl5t
title: Modelling Time within a Strongly Typed Database
desc: ''
updated: 1712869544138
created: 1697478474599
---

- url: https://medium.com/vaticle/modelling-time-within-a-strongly-typed-database-55ba91ecad62
- [[c.mention]] [[ar.a-brief-ontology-of-time]]

## Summary

  - various complexities can arise in modelling time-based data, including:
    1. Storage and Indexing: How to store time data fields so they can be accessed quickly
    2. Division and Aggregation: The smallest sensible time increment, and aggregation methods
    3. Multiple Timelines: Dealing with changing data
    4. Slowly Changing Dimensions: Classifying responses to temporal data changes
    5. Temporally Variable Schema and Data: Capturing schema and data changes
    6. Mining Temporal Relations: Methods of relating times to other times (e.g. before, after etc.)
  

## Issues

- What is the point of intIndex?

## Highlights

- "I personally use lists a lot, as well as dicts, for storage in TypeQL, and there are two circumstances:

    I insert an entire list at once, for example, a session in a log with events, and in this case, I use a dummy “stop” value at the end of each list, so it is easy to get.
    Insert items in a list incrementally, as shown above; in this case, I would match out the index of the current record, add 1 to it (in the client) and insert it in the new list item."
- "Indexing a single year needs to take account of ~3 x 10¹⁰ unique variations... TypeQL has unique capabilities that enable us to take advantage of this problem since attributes can own other attributes and have unique values. These capabilities enable us to form a composite index on time (a set of buckets using integers), taking the indexing requirement for a single year of microseconds down to 1,188 unique values."


## Text


