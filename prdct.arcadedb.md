---
id: l9iuu3zbft8356ka2cbzb00
title: ArcadeDB
desc: 'Multi-Model DB: Graph, Document, Key/Value, Search-Engine, Time-Series, and Vector-Embedding'
updated: 1706279564029
created: 1696481284791
---

- [[c.software.database.multi-model]]  [[c.software.database.graph.property]] [[c.software.database.embedded]] [[c.software.database.vector]]
- repo: https://github.com/ArcadeData/arcadedb
- [[p.forkOf]] [[prdct.orientdb]]
- written-in: java 
- [[p.compatibleWith]] [[prdct.cypher]] [[prdct.tinkerpop]]/[[prdct.gremlin]] [[prdct.redis]] [[prdct.postgres]]
- [[p.supports]] [[t.cs.gis.geospatial-querying]] [[t.cs.data.vector-embedding]]
- embed in JVM, so [[p.compatibleWith]] scala #groovy #kotlin #clojure

## Pro

- jvm-embeddable!
- ArcadeDB’s document model also adds the concept of a "Relationship" between documents. With ArcadeDB, you can decide whether to embed documents or link to them directly. When you fetch a document, all the links are automatically resolved by ArcadeDB. This is a major difference to other document databases, like MongoDB or CouchDB, where the developer must handle any and all relationships between the documents herself.
- in the key-value store, it supports documents and graph elements as values

## Con

- One edge can only connect two vertices. (no hypergraph/metagraphs)

## Questions

- are the different modes using completely separate data?
  - t.2024.01.26: yes, documents, edges and vertices are different types of records
- presumably properties can't refer to vertexes
  - t.2024.01.26: maybe not in a direct way, but you could use text

## Comparison

### vs [[prdct.neo4j]]

- "Neo4j supports multiple labels per node, while in ArcadeDB a node (vertex) must have only one type. The Neo4j importer will simulate multiple labels by creating new types with the following name: <label1>[_<labelN>]*."

## References

- [TinkerPop Wide: ArcadeDB - a Multi-Model Database with Gremlin](https://www.youtube.com/watch?v=X6qC-P-pkgs)
- https://www.linkedin.com/pulse/experience-using-arcadedb-modelling-tool-vineeth-joseph/
  - mentioned issues:
    - no versioning
    - no constraints over edge types
    - no renaming properties