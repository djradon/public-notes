---
id: 2a9xr9s81spagppn7iywlls
title: Apache Samza
desc: ''
updated: 1715627059966
created: 1715626830130
---

- topics: [[t.cs.data.materialized-view]]

## Description

- If you use Kafka to implement the log, how do you implement these materialized views? That’s where Apache Samza comes in. It’s a stream processing framework that is designed to go well with Kafka. With Samza, you write jobs that consume the events in a log, and build cached views of the data in the log. When a job first starts up, it can build up its state by consuming all the events in the log. And on an ongoing basis, whenever a new event appears in the stream, it can update the view accordingly. The view can be any existing database or index — Samza just provides the framework for processing the stream.



## References

- https://www.confluent.io/blog/turning-the-database-inside-out-with-apache-samza/