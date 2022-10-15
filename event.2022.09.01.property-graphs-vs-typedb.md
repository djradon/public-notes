---
id: w9ww9kr78v1vihvsxfznwxc
title: Property Graphs Vs Typedb
desc: ''
updated: 1662051674484
created: 1662050035757
---


- [[p.hostedBy]] [[user.tomas-sabat]]
- "strongly-typed database", but close to [[t.cs.data.DBMS.graph]]
- modeling complex data is difficult in graph (although easy to start)
  - "complex data" means a lot of types
    - relation types
    - entity types
- typedb is a graph engine under the hood, on top is the type system
- ![](/assets/images/2022-09-01-09-40-25.png)
  - property graphs: directional, binary, static
- typedb:
  - ![](/assets/images/2022-09-01-09-41-14.png)
  - hyper-relations allow:
    - ternary
    - no need for reification
    - nested relations ()
  - type hierarchys
    - in cypher, can't enforce labellings (which apparently is how you do types)
- Inferencing
  - most under-rated features of typedb
  - not machine learning, based on symbolic logic/deductive logic

Questions:
- why "locating" instead of located
- rule describes a pattern
  - ![](/assets/images/2022-09-01-10-00-20.png)