---
id: g2oqhue8elf7pcw735vzdzc
title: Virtual Threads
desc: ''
updated: 1706388913468
created: 1700161663502
---

## Use cases

- "If your application frequently performs heavy computation for very long durations, then virtual threads may be a bad fit to begin with because your system may easily become overcommitted by orders of magnitude."
- "If you're using SQLite or RocksDB, think carefully before adopting virtual threads."

## Comparisons

### vs Deno/Web Workers

- "Performance Management and Scalability:

    Java Virtual Threads: They are designed to be lightweight and highly scalable, especially for IO-bound tasks. The JVM manages these threads efficiently, allowing for the creation of thousands to millions of concurrent threads with a much lower memory footprint compared to traditional threads.
    Deno Web Workers: While powerful for CPU-bound tasks and parallel processing, each worker is a heavier construct compared to a Virtual Thread. This means that while they're excellent for offloading intensive tasks, they might not be as scalable as Virtual Threads for handling many small, concurrent tasks.

  Concurrency Model:

    Java Virtual Threads: They offer a straightforward model for writing concurrent code, similar to traditional threading but with a much lower overhead. This makes them ideal for applications with a large number of concurrent, mostly idle tasks.
    Deno Web Workers: They follow a message-passing model which can be more robust in terms of avoiding shared state problems, but it might require a different way of thinking about problem-solving, particularly for those used to shared-state concurrency models."
      - @chatgpt.4

## Resources

- https://spring.io/blog/2022/10/11/embracing-virtual-threads
- https://dev.to/devsegur/java-virtual-threads-vs-kotlin-coroutines-4ma8
- https://itnext.io/kotlin-coroutines-vs-java-virtual-threads-a-good-story-but-just-that-91038c7d21eb