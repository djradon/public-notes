---
id: sc9eqyn549lgihbdol3mmkn
title: Kotlin
desc: ''
updated: 1724890522102
created: 1698186020714
---

- [[p.publishedBy]] [[org.jetbrains]]

## Features

- compatibility with Java
  - "Kotlin seamlessly interacts with Java classes and methods, and vice versa, allowing for a smooth transition to the new language without the need to rewrite existing code."
- extensions allow adding new functions to existing classes without modifying them


### Coroutines

- "2. Conceptually Coroutines are very similar to VirtualThreads. The identical parts are: lightweight threads and structured concurrency. But there are also some differences:
  - Coroutines are more feature rich than what Loom offers now, namely:

    - context propagation (meaning let the same context, like a MDC, Transaction etc. be propagated across several Coroutines) is fully embedded in Coroutines. Loom is still experimenting with this part, which they call scope variables.

    - Cancellation: Part of the Contract Coroutines offer is cancellation, no matter how nested a process tree might be. This is and will not be available in Loom. In certain use-cases this is a big omission for Loom."[^1]


### Nullable Types

In Java, you need to explicitly check for null before accessing an object to avoid `NullPointerException`. This often leads to verbose null-checking code.

```kotlin
val name: String? = null
println(name?.length ?: "Name is null")
```

Kotlin uses the safe call operator `(?.)` and the Elvis operator `(?:)` to handle nullables concisely. This line safely accesses the length if `name` is not null, or otherwise prints `"Name is null"`. In Kotlin, the safe call operator, `?.`**,**  and the `?:` operator are used for default values, simplifying null handling.

## Related

- [[prdct.arrow-kt]]

## References

- [^1]: https://spring.io/blog/2022/10/11/embracing-virtual-threads
- https://itnext.io/kotlin-coroutines-vs-java-virtual-threads-a-good-story-but-just-that-91038c7d21eb
- https://dzone.com/articles/migrating-microservices-from-java-to-kotlin