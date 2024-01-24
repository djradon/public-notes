---
id: l9iuu3zbft8356ka2cbzb00
title: ArcadeDB
desc: ''
updated: 1706052234029
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

## Questions

- are the different modes using completely separate data?
- presumably properties can't refer to vertexes

## References

- [TinkerPop Wide: ArcadeDB - a Multi-Model Database with Gremlin](https://www.youtube.com/watch?v=X6qC-P-pkgs)
- https://www.linkedin.com/pulse/experience-using-arcadedb-modelling-tool-vineeth-joseph/
  - mentioned issues:
    - no versioning
    - no constraints over edge types
    - no renaming properties