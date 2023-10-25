---
id: m6bdg4qh72u56bqpiweijtz
title: CRDT
desc: 'conflict-free replicated data type'
updated: 1682972651794
created: 1682972612189
---

## Summary

-   The application can update any replica independently, [concurrently](https://en.wikipedia.org/wiki/Concurrent_computing "Concurrent computing") and without [coordinating](https://en.wikipedia.org/wiki/Concurrency_control "Concurrency control") with other replicas.
-   An algorithm (itself part of the data type) automatically resolves any inconsistencies that might occur.
-   Although replicas may have different state at any particular point in time, they are guaranteed to eventually converge.