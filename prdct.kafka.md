---
id: vc2zh595cbr9z70mlf45qyh
title: Kafka
desc: ''
updated: 1715633321732
created: 1662589413388
---

- [[c.software.data-framework.streaming]]
- [[p.hostedBy]]
  - [[prdct.upstash]] for free
- [[p.supports]] [[prdct.cloudevents]]
  - https://github.com/cloudevents/spec/blob/main/cloudevents/bindings/kafka-protocol-binding.md
- related: [[prdct.samza]]

![[prdct.redpanda#similar]]

### Managed
![[prdct.azure.event-hubs#^ls3s1l3vm1hl]]


## Pros

## Cons

- massive
- [[t.cs.sd.event-sourcing]] is not a top-level architecture [^1]

## Features

- [dynamic routing](https://www.confluent.io/blog/putting-events-in-their-place-with-dynamic-routing/)
- **compaction** 

## Use Cases

- "Kafka is not an event store; rather, it is an enabler for building event stores."
  - https://towardsdatascience.com/the-design-of-an-event-store-8c751c47db6f

## Comparisons

![[prdct.nats#kafka-vs-nats]]

## Learning Resource

## [[c.footnote]]

[^1]: https://itnext.io/event-sourcing-why-kafka-is-not-suitable-as-an-event-store-796e5d9ab63c