---
id: yv6xjfh2powsn8gimdpbb7p
title: Type Theory as the Unifying Foundation for Modern Database
desc: ''
updated: 1701364690529
created: 1700154014209
---
  
- [[p.hostedBy]] @alvin-leung
- [[c.actor.speaker]] @christoph-dorn

- problems with relational, graph, document, triplestore/rdf:
  - mismatch of conceptual and logical model
    - object-relational mismatch, reification, multi-valued attributes
    - lack of support for polymorphic and highly connected data
  - no easy system extensibility and maintability
    - imperative, long, complex, brittle queries
    - no facility for composable, generic queries that are highly reusable
    - ![](/assets/images/2023-11-16-09-07-33.png)
  - semantic data integrity is easily violated
    - no meaningful data validation due to no sufficiently expressive schemas
    - data redundancies need to be carefully synced
      - ![](/assets/images/2023-11-16-09-08-22.png)
- ![](/assets/images/2023-11-16-09-09-55.png)
- "general theory of composable structure" is a natural start point for re-inventing
  - ![](/assets/images/2023-11-16-09-10-48.png)
- typedb conceptual data model is a unification of relational, graph, and document
- Modernization of Math
  - classical relational algebra: sets and relations (aka predicates and predicate logic)
  - modeling everything in sets and relations is non-practical
  - composable systems: types and dependent type
    - facts become data in types that can be referenced
    - dependencies can be composed
    - [[book.practical-foundation-of-modern-mathematics]]
- crash course in type theory
  - a type is a description of a domain that a variable can range over
    - dependent types have definitions that include other variables
  - in predicate logic, dependent pair types can compose
- ![](/assets/images/2023-11-16-09-24-46.png)
- type polymorphism
  - inheritance polymorphism
  - interface "
  - parametric "
    - defines generic functionality for (variabilized) types, enabling semantically generic queries
- reasoning engine
- result: a unifying foundation for modern database
  - ![](/assets/images/2023-11-16-09-42-40.png)
- summary:
  - [[prdct.typedb]] implements the unifying type-theoretic, polymorphic paradigm
  - so extensible, adaptable, safe and robust
  - fast-evolving ecosystem