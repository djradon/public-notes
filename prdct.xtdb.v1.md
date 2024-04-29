---
id: lq10bixve20i64veu1k5fx0
title: XTDB V1
desc: Bitemporal and dynamic relational database for SQL and Datalog
updated: 1713481106503
created: 1705951600818
---


- [[c.software.database.bitemporal]]
- url: https://xtdb.com/
- repo: https://github.com/xtdb/xtdb
- similar: [[prdct.xtdb.v2]]
- related: [[prdct.site]] [[prdct.crux-geo]] [[prdct.biff]]
- supports:
  - storage: [[prdct.lmdb]] [[prdct.rocksdb]]

## Features

### Temporality

Valid time is valuable for tracking a consistent view of the entire state of the database, however, unless you explicitly include a timestamp or other temporal component within your documents you cannot currently use this information about valid time inside of your Datalog queries.

Domain time or "user-defined" time is simply the storing of any additional time-related information within your documents, for instance `valid-time`, `duration` or timestamps relating to additional temporal life-cycles (e.g. decision, receipt, notification, availability).

Queries that use domain times do not automatically benefit from any kind of native indexes to support efficient execution, however XTDB encourages you to build additional layers of functionality to do so. See [decorators](https://github.com/crux-labs/crux-decorators) for examples.

  - t.2024.04.18.15 (I think decorators are no longer supported in v2, "Rather than supporting arbitrary Clojure functions, queries in XTDB 2 now use an XT standard library of functions, drawn from the SQL standard.")

- "bring your own schema (enforcement)"

- [[prdct.corda]] blockchain support 
  - "The XTDB team has officially released an alpha of xtdb-corda, a library which augments the Corda blockchain with XTDB Datalog query capabilities. Using this module, verified Corda transactions are automatically piped into an XTDB node for seamless bitemporal graph queries. Remy Rojas recently wrote about the module in Bridging the Blockchain / Database Divide."

## Resources

### Learning Resources

- https://nextjournal.com/learn-xtdb-datalog-today/learn-xtdb-datalog-today
- https://dev.to/marleyspoon/bitemporality-or-how-to-change-the-past-3k4f

## References

- https://www.reddit.com/r/TerminusDB/comments/119g613/terminusdb_vs_xtdb/
- https://www.reddit.com/r/Database/comments/reiadb/best_database_to_store_ordered_hierarchical_data/
- https://news.ycombinator.com/item?id=35733515
- https://biffweb.com/p/xtdb-compared-to-other-databases/

