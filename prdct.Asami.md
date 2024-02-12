---
id: g4GbScDY7ILBGQSegwsyx
title: Asami
desc: ''
updated: 1638127452118
created: 1636380102275
---

- dead
- [[p.hasRepository]] https://github.com/threatgrid/asami
- [[p.hasComponent]] [[prdct.loom]]
- [[p.instanceOf]] [[t.cs.data.DBMS.graph]]
- written-in: [[t.cs.languages.Clojure]]
- [[p.hasFeature]]
  - Clojure and ClojureScript: Asami runs identically in both systems.
  - Schema-less: Asami does not require a schema to insert data.
  - Query planner: Queries are analyzed to find an efficient execution plan. This can be turned off.
  - Analytics: Supports fast graph traversal operations, such as transitive closures, and can identify subgraphs.
  - Integrated with Loom: Asami graphs are valid Loom graphs, via Asami-Loom.
  - [[Open World Assumption|t.cs.web.w3c.rdf.open-world-assumption]]: Related to being schema-less, Asami borrows semantics from RDF to lean towards an open world model.
  - Pluggable Storage: Like Datomic, storage in Asami can be implemented in multiple ways. There are currently 2 in-memory graph systems, and durable storage available on the JVM
