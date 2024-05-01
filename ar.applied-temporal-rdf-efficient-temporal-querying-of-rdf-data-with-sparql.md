---
id: 8q3wkicfurf0iva76qwio2k
title: Applied Temporal Rdf Efficient Temporal Querying of Rdf Data with Sparql
desc: >-
  Each time interval is represented by exactly one named graph, where all
  triples belonging to this graph share the same validity period.
updated: 1713376324244
created: 1712869321664
---

- https://drive.google.com/open?id=1-V3E93i9gqdOEHzVMyiHJMTGjahh62GU&usp=drive_fs

## Abstract

Many applications operate on time-sensitive data. Some of these data are only valid for certain intervals (e.g., job-assignments, ver- sions of software code), others describe temporal events that happened at certain points in time (e.g., a person’s birthday). Until recently, the only way to incorporate time into Semantic Web models was as a data type property. Temporal RDF, however, considers time as an additional dimension in data preserving the semantics of time. 

In this paper we present a syntax and storage format based on named graphs to express temporal RDF. Given the restriction to preexisting RDF-syntax, our approach can perform any temporal query using stan- dard SPARQL syntax only. For convenience, we introduce a shorthand format called τ -SPARQL for temporal queries and show how τ -SPARQL queries can be translated to standard SPARQL. Additionally, we show that, depending on the underlying data’s nature, the temporal RDF ap- proach vastly reduces the number of triples by eliminating redundancies resulting in an increased performance for processing and querying. Last but not least, we introduce a new indexing approach method that can significantly reduce the time needed to execute time point queries (e.g., what happened on January 1st).

## Highlights

### Related Approaches

#### Temporal Extensions

- Welty and Fikes [6], Kim et al. [7] and the tOWL [8] project aim at introducing temporal entities into OWL.

#### Time Encoded in the Data Model

- lose the semantics of time
- temporal properties can't be attached to relations

#### Graph Versions and Version Management Systems

- SemVersion uses its own data model that contains the user’s ontology and its evolution. Our proposi- tion is not to introduce a new data model, but, storing the elements of the users’ data model inside different named graphs according to their temporal context.

### Proposed Temporal Syntax

- As in most of the approaches dealing with temporal entities, we model time as a 1-dimensional discrete value (i.e. no branching time)
- we extended OWL- Time with a new date format type called IntegerTime to express non-calendaric time representations such as version numbers.
- We refer to a set of temporally related named graphs as a temporal graph. Each time interval is represented by exactly one named graph, where all triples belonging to this graph share the same validity period.
  