---
id: wvhaqos751qey64k9apdoyx
title: Why We Need a Polymorphic Database
desc: ''
updated: 1701416370000
created: 1701363883374
url: https://typedb.com/lectures/why-polymorphic-database
presenter: "@james-whiteside"
attendee_count: 39
host: "@alvin-leung"
---



## Issues

- document paradigm references via IDs:
  - they're not pointers, they're just values and doc dbs aren't designed to use references
  - "document object mismatch"
- graph dbs have attributes as part of node structure, but relationships (modeled as an edge) leads to object-graph mismatch because a node and two edges represent an atomic relationship; also no n-ary relations, nested relations, or undirected/two-way relations
  - ? but in object models, two way relations might get modelled with two directions

## Semantic Integrity

- matching integrity of polymorphic data
- inheritance polymorphism
  - with relational, patterns are:
    - single-table pattern (big table with fields for each type)
      - can't control "type integrity" for subtypes
    - concrete-table pattern (one table for employees, one for contractors)
      - can't enforce global uniqueness with IDs, so all references need multiple 
    - class-table pattern (employee table, permanent employees table, contractors table)
      - can't enforce object identity
    - rows are one-dimensional
  - with documents
    - "polymorphic pattern" (coupal et al, 2023)
    - maintaining consistency is difficult
    - using ObjectIDs are values, not pointers
      - so deleting the target, there's a null reference
        - i.e., no cascading delete
  - graphs
    - ![](/assets/images/2023-11-30-09-29-47.png)
    - not possible to control the types of relationships that can be made between nodes
      - so cannot enforce semantic integrity

## Example: Simple Filesystem

![](/assets/images/2023-11-30-09-32-04.png)
![](/assets/images/2023-11-30-09-38-17.png)
![](/assets/images/2023-11-30-09-39-13.png)
![](/assets/images/2023-11-30-09-47-34.png)

- for docDBs
  - return types are hardcoded with unmions and lookups
  - attribute interfaces are hardcoded
  - ?
- for graphDBs
  - can use generic pattern matching for multiple return types, but
  - attribute interfaces hardcoded
  - type inheritance hardcoded
- all require metadata hardcoded into polymorphic queries becuase
  - queries do not represent the natural language meaning/intent

## Summary

![](/assets/images/2023-11-30-09-54-25.png)

## Questions

- Does TypeDB have Object-PolymorphicDB mapping technology (OPM?), a la ORM/ODM/OGM
  - not yet
- Why not just use in-memory object models with object serialization (say, to the filesystem) and then for requests, use streams/filters and programmatic/native code for queries and semantically-consistent updates?
  - (misunderstood, but) databases are good for sharing the data, persisting it, etc. 
- it seems like you should be able to just update the string-based reference identity everywhere it occurs, just like a dendron Move Note or Refactor
- 