---
id: ud9uiapm83zxmmc5mdc3w48
title: Materialized View
desc: ''
updated: 1715627125651
created: 1715627060417
---

## Comparisons

### Materialized Views vs Read-Through Cache

-   With the materialized view, there is a principled _translation process_ from the write-optimized data in the log into the read-optimized data in the view. That translation runs in a separate process which you can monitor, debug, scale and maintain independently from the rest of your application. By contrast, in the typical read-through caching approach, the cache management logic is deeply intertwined with the rest of the application, it’s easy to introduce bugs, and it’s difficult to understand what is happening.
-   A cache is filled on demand when there is a cache miss (so the first request for a given object is always slow). By contrast, a materialized view is _precomputed_, i.e. its entire contents are computed before anyone asks for it — just like a secondary index. This means there is no such thing as a cache miss: if an item doesn’t exist in the materialized view, it doesn’t exist in the database. There is no need to fall back to some kind of underlying database.
-   Once you have this process for translating logs into views, you have great flexibility to create new views: if you want to present your existing data in some new way, you can simply create a new stream processing job, consume the input log from the beginning, and thus build a completely new view onto all the existing data. (If you think about it, this is pretty much what a database does internally when you create a new secondary index on an existing table.) You can then maintain both views in parallel, gradually move applications to the new view, and eventually discard the old view. No more scary stop-the-world schema migrations.
-   

## References

- https://www.confluent.io/blog/turning-the-database-inside-out-with-apache-samza/