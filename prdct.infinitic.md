---
id: 9lz4tx65j4mrzco11tvp7y1
title: Infinitic
desc: 'Add durable executions capabilities to your existing event streaming platform. Build business processes that endure failures, crashes, or server outages'
updated: 1715286757498
created: 1713560098986
---

- [[c.Software.messaging.middleware]]
- similar: [[prdct.catalyst]]
- written-in: kotlin
- supports: java
- requires: 
  - [[prdct.pulsar]] 
  - [[prdct.redis]] or [[prdct.MySQL]]

## Terms

- **Services** primarily defined by their interfaces and are invoked using event-based RPC
- **Tasks** a method within a service class. It can be anything from a database operation, an API call, to any complex action specific to your domain.
- 


## Orchestration

![[t.cs.sd.architecture.orchestration#^21ydosqb6dt1]]

## References

- [[ar.medium.the-way-we-are-building-event-driven-applications-is-misguided]]