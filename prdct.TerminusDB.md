---
id: f1NRb172HfsDVGSJiwQqZ
title: TerminusDB
desc: >-
  a labeled, directed, and edge-labeled graph engine where segments of the graph
  are JSON documents: the graph is an interconnected series of documents
updated: 1701464619290
created: 1637799658994
type: "[[c.software.database.graph.rdf]]"
had_query_language_support: ["[[prdct.graphql]]", "[[prdct.woql]]"]
had_client_language_support: [python, javascript]
author: "@kevin-feeny"
---

- [[p.builtWith]] [[prdct.rdf]]
- [[p.similarTo]]
  - [[prdct.typedb]]
  - [[prdct.fluree]]

## Features

-   The [db schema 8](https://terminusdb.com/docs/schema) is defined in [[prdct.owl]]
-   Most operation occurs in-memory, but is persisted in a forward-only log (similar to git)
-   This “git-for-data” approach allows branch, merge, squash, rollback, diff, blame, and time-travel, etc.
-   [[prdct.json-ld]] is interchange format, suitable for web, but editing in turtle is possible
-   You can query any part of a graph and retrieve as a JSON-LD document (serialized to the depth you want)
-   Query format is also JSON-LD, making queries composable and you can store/query queries like normal data
-   Client-side the queries are created using fluent JS (for web devs) and/or Ruby (for data scientists)
-   Provides transaction processing and updates using immutable database data structures
-   Through this immutability the db regains full ACID support

## Resources

- https://medium.com/terminusdb/6-reasons-why-terminusdb-is-the-right-toolkit-to-build-collaborative-apps-6fb9ae96ff4
- https://terminusdb.com/blog/loading-data-in-turtle-rdf-format-to-terminusdb/
- https://forum.solidproject.org/t/terminusdb-a-delightful-database-for-linked-data/3140
  - mentioned: https://news.ycombinator.com/item?id=22867767
- https://terminusdb.com/blog/graphql-query/