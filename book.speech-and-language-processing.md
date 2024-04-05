---
id: yoo3uiiltifai2uxn6zma0a
title: Speech and Language Processing
desc: ''
updated: 1712347026355
created: 1712344019585
---

### Chapter 20: Semantic Role Labelling

- url: https://web.stanford.edu/~jurafsky/slp3/old_oct19/20.pdf
- deep roles are specific to each event; Breaking events have Breakers, Opening events have Openers, and so on.

#### Thematic Roles

Thematic Role Definition
AGENT The volitional causer of an event
EXPERIENCER The experiencer of an event
FORCE The non-volitional causer of the event
THEME The participant most directly affected by an event
RESULT The end product of an event
CONTENT The proposition or content of a propositional event
INSTRUMENT An instrument used in an event
BENEFICIARY The beneficiary of an event
SOURCE The origin of the object of a transfer event
GOAL The destination of an object of a transfer event

Thematic Role Example
AGENT The waiter spilled the soup.
EXPERIENCER John has a headache.
FORCE The wind blows debris from the mall into our yards.
THEME Only after Benjamin Franklin broke the ice...
RESULT The city built a regulation-size baseball diamond...
CONTENT Mona asked “You met Mary Ann at a supermarket?”
INSTRUMENT He poached catfish, stunning them with a shocking device...
BENEFICIARY Whenever Ann Callahan makes hotel reservations for her boss...
SOURCE I flew in from Boston.
GOAL I drove to Portland.

#### Semantic Roles

- are defined, not by necessary and sufficient conditions, but rather by a set of heuristic features that accompany more agent-like or more patient-like meanings
- PropBank uses both proto-roles and verb-specific semantic roles. FrameNet uses semantic roles that are spe- cific to a general semantic idea called a frame.

##### PropBank
Arg0: causer (e.g. of increase)
Arg1: thing (e.g. increasing)
Arg2: amount (e.g.increased) by, EXT, or MNR
Arg3: start point
Arg4: end point

###### Arg-Ms
TMP when? yesterday evening, now
LOC where? at the museum, in San Francisco
DIR where to/from? down, to Bangkok
MNR how? clearly, with much enthusiasm
PRP/CAU why? because ... , in response to the ruling
REC themselves, each other
ADV miscellaneous
PRD secondary predication ...ate the meat raw


##### FrameNet

- Whereas roles in the PropBank project are specific to an individual verb, roles in the FrameNet project are specific to a frame. What is a frame? Consider the following set of words: reservation, flight, travel, buy, price, cost, fare, rates, meal, plane There are many individual lexical relations of hyponymy, synonymy, and so on between many of the words in this list. The resulting set of relations does not, however, add up to a complete account of how these words are related. They are clearly all defined with respect to a coherent chunk of common-sense background information concerning air travel. We call the holistic background knowledge that unites these words a frame 

- Some of the semantic roles (frame elements) in the frame are.... separated into core roles, which are frame specific and non-core roles, which are more like the Arg-M arguments in PropBank, expressing  general properties of time, location, and so on

Core Roles
ATTRIBUTE The ATTRIBUTE is a scalar property that the ITEM possesses.
DIFFERENCE The distance by which an ITEM changes its position on the scale.
FINAL STATE A description that presents the ITEM’s state after the change in the ATTRIBUTE’s value as an independent predication.
FINAL VALUE The position on the scale where the ITEM ends up.
INITIAL STATE A description that presents the ITEM’s state before the change in the ATTRIBUTE’s value as an independent predication.
INITIAL VALUE The initial position on the scale from which the ITEM moves away.
ITEM The entity that has a position on the scale.
VALUE RANGE A portion of the scale, typically identified by its end points, along which the values of the ATTRIBUTE fluctuate.

Some Non-Core Roles
DURATION The length of time over which the change takes place.
SPEED The rate of change of the VALUE.
GROUP The GROUP in which an ITEM changes the value of an
ATTRIBUTE in a specified way

#### Selectional Restrictions

- SRs are a semantic type constraint that a verb imposes on the kind of concepts that are allowed to fill its argument
roles.
- In the earliest implementations, selectional restrictions were considered strict con- straints on the kind of arguments a predicate could take
  - it became clear that these selectional restrictions were better represented as preferences rather than strict constraints
    - selectional restriction violations (like inedible arguments of eat) often occur in well-formed sentences, for example because they are negated (20.36), or because selectional restrictions are overstated
- selection preference strength defines the amount of information that a predicate tells us about the semantic class of its argu-
ments. 
- Most semantic role labeling schemes only work within a single sentence, fo- cusing on the object of the verbal (or nominal, in the case of NomBank) predicate. However, in many cases, a verbal or nominal predicate may have an implicit argu- ment: one that appears only in a contextual sentence, or perhaps not at all and must be inferred. In the two sentences This house has a new owner. The sale was finalized 10 days ago. the sale in the second sentence has no ARG1, but a reasonable reader would infer that the Arg1 should be the house mentioned in the prior sentence. Find- ing these arguments, implicit argument detection (sometimes shortened as iSRL)

#### Primitive Decomposition of Predicates

- The decompositional approach asserts that a single state-like predicate associ- ated with open underlies all of these examples. The differences among the meanings of these examples arises from the combination of this single predicate with the prim- itives CAUSE and BECOME. While this approach to primitive decomposition can explain the similarity be- tween states and actions or causative and non-causative predicates, it still relies on having a large number of predicates like open. More radical approaches choose to break down these predicates as well. One such approach to verbal predicate de- composition that played a role in early natural language understanding systems is conceptual dependency (CD), a set of ten primitive predicates:

Primitive Definition
ATRANS The abstract transfer of possession or control from one entity to
another
PTRANS The physical transfer of an object from one location to another
MTRANS The transfer of mental concepts between entities or within an
entity
MBUILD The creation of new information within an entity
PROPEL The application of physical force to move an object
MOVE The integral movement of a body part by an animal
INGEST The taking in of a substance by an animal
EXPEL The expulsion of something from an animal
SPEAK The action of producing a sound
ATTEND The action of focusing a sense organ

The verb brought is translated into the two primitives ATRANS and PTRANS to indicate that the waiter both physically conveyed the check to Mary and passed control of it to her.
