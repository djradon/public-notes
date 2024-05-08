---
id: s591odjqme558glh9cx4r9u
title: Brackit
desc: 'Query processor with proven optimizations, ready to use for your JSON store to query semi-structured data with JSONiq. Can also be used as an ad-hoc in-memory query processor. '
updated: 1715189226191
created: 1715188917271
---

- repo: https://github.com/sirixdb/brackit

## Mission

Our work is guided by the following basic questions:

-   What is an appropriate level of abstraction for accessing and (de-)composing semi-structured data? How should we represent semi-structured data with deep nestings and varying sizes at runtime? How can we support native operations and alternative access methods, i.e., indexes etc.?
-   How should we represent queries, whole scripts, and user-defined functions to leverage proven optimization techniques from both query languages (e.g., predicate-pushdown, join ordering, optimized aggregation) and programming languages (e.g., tail recursion)?
-   How can we support different evaluation philosophies (pull-based, push-based, mixed push/pull) and proven query algorithms?. How can we (automatically) exploit partitioned data, parallel hardware and query-inherent parallelism?
-   How can we incorporate physical and system-specific properties (e.g., memory locality) in the compilation and evaluation process?

## References

- https://github.com/sirixdb/brackit/blob/master/mission.md