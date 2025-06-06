---
id: Ej3tbATdXqr9WwU1ASciK
title: TypeDB
desc: >-
  Composed of entity, relationship, and attribute types, as well as type
  hierarchies, roles, and rules
updated: 1730843232321
created: 1643725570180
---

- [[c.software.database.graph]] [[c.Software.Database.graph.hypergraph]]
- aka: grakn
- [[p.ownedBy]] [[org.vaticle]]
- [[p.hasRepository]] https://github.com/vaticle/typedb
- [[p.hasRelatedSolution]] [[prdct.typeql]] [[prdct.blitz-orm]]
- written-in: java
- [[p.builtOn]] 
  - [[prdct.rocksdb]]
  - [[prdct.grpc]]
    - [[p.hasSource]] https://docs.vaticle.com/docs/client-api/new-client
  - [[prdct.janusgraph]] (https://graphsandnetworks.com/typedb-previously-grakn-ai/)
  - [[prdct.speedb]]

## [[p.hasConcept]]

- "Concept Architecture"
  - ![](/assets/images/2022-03-14-14-26-10.png)
  - ![](/assets/images/2023-09-21-22-03-51.png)
  - ![](/assets/images/2023-09-21-22-19-16.png)

### Thoughts

- a little unusual for a thing to be a concept. My water bottle is not really a concept.
  - https://hydeandrugg.wordpress.com/2016/01/24/things-concepts-and-words/

## Use Cases

- [[prdct.typedb-data-cti]]

## Tips

- When inserting instances of a relation, it is not necessary to define all of its role players. But this represents an incomplete information state, such as a marriage in which only one of the spouses is known.
- 


## Issues

- [Run TypeDB Studio in a web browser](https://github.com/vaticle/typedb-studio/issues/118)
  - we have recently rewritten Workbase as Studio, and it is no longer an Electron app
- how do you establish order?
  - use a property
    - https://forum.vaticle.com/t/how-to-best-represent-the-order-of-nodes-on-an-edge/279

## Modelling

- entity: 
  - anything physical
  - anything that exists logically but doesn't require involvement of other things
  - concrete
  - /proper/common/abstract/collective
  - relations should be "abstract nouns" or "transitive verbs that can accept 2 or more argument"
- no equivalanet of blank node (no open world), but you could do "entity with no URI is unspecified"
- "GRAKN.AI uses “hypergraphs” instead of vanilla digraphs to model their knowledge, although under the hood, they map these hypergraphs to digraphs before persisting to whatever vendor DB using Apache TinkerPop."
  - https://discuss.dgraph.io/t/hypergraphql-query-language/2123

### Temporal Modelling

- [[ar.medium.vaticle.modelling-time-within-a-strongly-typed-database]]
- t.2024.01.15: "expressions don't have datetime computation functionality yet" 


## Resources

- https://victormorgante.medium.com/query-generation-for-typedb-67c7b4a88ee2
  - "TypeDB approaches the database market conceptualised as both a database and a rules-based knowledge graph combined as one. Operating over a key/value store the database encompasses the same sort of architecture used by FactEngine to effectively turn any compatible database into a natural language/
- https://graphsandnetworks.com/typedb-previously-grakn-ai/
- [[ar.towardsdatascience.an-enterprise-data-stack-using-typedb]]
- https://blog.vaticle.com/what-is-a-knowledge-graph-5234363bf7f5
- https://forum.typedb.com/t/rdf-uris-as-attributes-of-all-types/433

- https://medium.com/vaticle/modelling-data-with-hypergraphs-edff1e12edf0
  - mentions [Knowledge Graph Representation: TypeDB or OWL?](https://medium.com/vaticle/knowledge-graph-representation-grakn-ai-or-owl-506065bd3f24)
- [Comparing Semantic Web Technologies to TypeDB](https://www.youtube.com/watch?v=LFgV7sCnOrE)
- [[ar.medium.vaticle.modelling-time-within-a-strongly-typed-database]]
- [How do actors enable and elegant and scalable reasoning engine](https://www.youtube.com/watch?v=fQ1faqMFq9E)
- https://typedb.com/blog/inference-in-typedb
- https://typedb.com/blog/modeling-collections-in-databases-relational-sql-vs-typedb 