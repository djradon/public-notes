---
id: Ej3tbATdXqr9WwU1ASciK
title: TypeDB
desc: >-
  Composed of entity, relationship, and attribute types, as well as type
  hierarchies, roles, and rules
updated: 1658325631761
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

## [[p.hasConcept]]

- "Concept Architecture"
  - ![](/assets/images/2022-03-14-14-26-10.png)
  - 

## [[p.hasUseCase]]

- [[soln.typedb-data-cti]]

## [[p.hasRelatedResource]]

- https://victormorgante.medium.com/query-generation-for-typedb-67c7b4a88ee2
  - "TypeDB approaches the database market conceptualised as both a database and a rules-based knowledge graph combined as one. Operating over a key/value store the database encompasses the same sort of architecture used by FactEngine to effectively turn any compatible database into a natural language/hypergraph database."
- https://graphsandnetworks.com/typedb-previously-grakn-ai/
- [[ar.towardsdatascience.an-enterprise-data-stack-using-typedb]]
- https://blog.vaticle.com/what-is-a-knowledge-graph-5234363bf7f5

## [[p.hasIssue]]

- [Run TypeDB Studio in a web browser](https://github.com/vaticle/typedb-studio/issues/118)
  - we have recently rewritten Workbase as Studio, and it is no longer an Electron app

## Modelling

- entity: 
  - anything physical
  - anything that exists logically but doesn't require involvement of other things
  - concrete
  - /proper/common/abstract/collective
  - relations should be "abstract nouns" or "transitive verbs that can accept 2 or more argument"

### Temporal Modelling L

- https://blog.vaticle.com/modelling-time-within-a-strongly-typed-database-55ba91ecad62
