---
id: Ej3tbATdXqr9WwU1ASciK
title: TypeDB
desc: >-
  Composed of entity, relationship, and attribute types, as well as type
  hierarchies, roles, and rules
updated: 1645297648723
created: 1643725570180
---

- [[p.alsoKnownAs]] grakn
- [[p.ownedBy]] [[org.vaticle]]
- [[p.hasRepository]] https://github.com/vaticle/typedb
- [[p.hasRelatedSolution]] [[soln.typeql]]
- [[p.writtenIn]] [[t.cs.language.Java]]
- [[p.builtOn]] 
  - [[soln.rocksdb]]
  - [[soln.grpc]]
    - [[p.hasSource]] https://docs.vaticle.com/docs/client-api/new-client


## [[p.hasUseCase]]

- [[soln.typedb-data-cti]]

## [[p.hasRelatedResource]]

- https://victormorgante.medium.com/query-generation-for-typedb-67c7b4a88ee2
  - "TypeDB approaches the database market conceptualised as both a database and a rules-based knowledge graph combined as one. Operating over a key/value store the database encompasses the same sort of architecture used by FactEngine to effectively turn any compatible database into a natural language/hypergraph database."

## [[p.hasIssue]]

- [Run TypeDB Studio in a web browser](https://github.com/vaticle/typedb-studio/issues/118)
  - we have recently rewritten Workbase as Studio, and it is no longer an Electron app
