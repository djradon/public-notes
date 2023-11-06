---
id: sc9eqyn549lgihbdol3mmkn
title: Kotlin
desc: ''
updated: 1699292177963
created: 1698186020714
---

- [[p.publishedBy]] [[org.jetbrains]]

## Features

### Coroutines

- "2. Conceptually Coroutines are very similar to VirtualThreads. The identical parts are: lightweight threads and structured concurrency. But there are also some differences:
-- Coroutines are more feature rich than what Loom offers now, namely:

--- context propagation (meaning let the same context, like a MDC, Transaction etc. be propagated across several Coroutines) is fully embedded in Coroutines. Loom is still experimenting with this part, which they call scope variables.

--- Cancellation: Part of the Contract Coroutines offer is cancellation, no matter how nested a process tree might be. This is and will not be available in Loom. In certain use-cases this is a big omission for Loom."[^1]

## Related

- [[prdct.arrow-kt]]

## References

[^1]: https://spring.io/blog/2022/10/11/embracing-virtual-threads