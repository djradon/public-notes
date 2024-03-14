---
id: lq10bixve20i64veu1k5fx0
title: Xtdb
desc: 'Bitemporal and dynamic relational database for SQL and Datalog'
updated: 1710451115930
created: 1705951600818
---

- [[c.software.database.bitemporal]]
- url: https://xtdb.com/
- repo: https://github.com/xtdb/xtdb
- similar: [[prdct.xtdb2]]
- related: [[prdct.site]] [[prdct.crux-geo]] [[prdct.biff]]
- supports:
  - storage: [[prdct.lmdb]] [[prdct.rocksdb]]

## Features

- bitemporal support (point-in-time querying and )
  - "Where XTDB has previously been optimized for point-in-time historical queries, v2 now supports ‘cross-time’ queries, e.g. temporal joins and temporal range scans. This unlocks the complete history of data for rich analysis.
  - 
We support the SQL:2011 standard for bitemporal functionality, and it’s built into the heart of XTQL too."

- "XTDB 2 will compute and maintain incremental indexes on-the-fly based on the raw data, so index updates will present far less operational impact. This also means the transaction log is now ~ephemeral in the new architecture (no more event-sourcing-style replays required, ever)."
- "bring your own schema (enforcement)"

- [[prdct.corda]] blockchain support 
  - "The XTDB team has officially released an alpha of xtdb-corda, a library which augments the Corda blockchain with XTDB Datalog query capabilities. Using this module, verified Corda transactions are automatically piped into an XTDB node for seamless bitemporal graph queries. Remy Rojas recently wrote about the module in Bridging the Blockchain / Database Divide."
- "[[t.cs.graph.temporal-joins]]"

## Resources

### Learning Resources

- https://nextjournal.com/learn-xtdb-datalog-today/learn-xtdb-datalog-today

## References

- https://www.reddit.com/r/TerminusDB/comments/119g613/terminusdb_vs_xtdb/
- https://www.reddit.com/r/Database/comments/reiadb/best_database_to_store_ordered_hierarchical_data/
- https://news.ycombinator.com/item?id=35733515
- https://biffweb.com/p/xtdb-compared-to-other-databases/