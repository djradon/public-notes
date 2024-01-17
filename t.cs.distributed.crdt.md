---
id: m6bdg4qh72u56bqpiweijtz
title: CRDT
desc: 'conflict-free replicated data type'
updated: 1705528203123
created: 1682972612189
---

## Summary

-   The application can update any replica independently, [concurrently](https://en.wikipedia.org/wiki/Concurrent_computing "Concurrent computing") and without [coordinating](https://en.wikipedia.org/wiki/Concurrency_control "Concurrency control") with other replicas.
-   An algorithm (itself part of the data type) automatically resolves any inconsistencies that might occur.
-   Although replicas may have different state at any particular point in time, they are guaranteed to eventually converge.
  
## Description

- objects can’t be destroyed but disabled. Moreover operations that impact the model must follow 3 constraints: they can be applied in any order (commutative and associative) and as many times as needed (idempotent, meaning that you can apply an operation twice and still have the same result as if you apply it once). The great thing is conflicts are then impossible: if you move an object that has just been “destroyed”, you’ll in fact move a “hidden” object. But as a result, your model will be monotonically growing, and designing operations with such constraints becomes quickly difficult with a part of research and risk associated with it.


## Resources

- https://irisate.com/collaborative-editing-solutions-round-up/