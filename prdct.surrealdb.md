---
id: p9dycdhtvdicli85iw40s7p
title: SurrealDB
desc: 'scalable, distributed, collaborative, document-graph database, for the realtime web'
updated: 1709228953893
created: 1689630910814
---

- url: https://surrealdb.com/
- repo: https://github.com/surrealdb/surrealdb
- written_in: rust
- supports: C#, javascript, rust, python, go, java

## Features

- graph support via "edge tables" [[t.cs.graph]]
  - https://surrealdb.com/docs/surrealql/statements/relate
  - Offer bi-directional querying.
  - Offer referential integrity.
  - Allow you to store data alongside the relationship.
- [[prdct.geojson]] geometries
- seems to take care of ORM/OGM mapping natively? https://docs.surrealdb.com/docs/integration/sdks/dotnet/

## References

- https://github.com/Laragear/Surreal/blob/master/README.md
- [In Search of an Efficient Data Structure
for a Temporal-Graph Database](https://surrealdb.com/static/whitepaper.pdf)
- https://surrealdb.com/blog/unlocking-streaming-data-magic-with-surrealdb-live-queries-and-change-feeds