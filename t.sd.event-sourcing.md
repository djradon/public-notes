---
id: prbis54rvnvjcg4y74map4h
title: Event Sourcing
desc: a different way of persisting data where data changes are saved in domain events
updated: 1669463459699
created: 1658585055608
---

- [[p.couldBeConfusedWith]] 
  - [[t.sd.architecture.cqrs]]
    - "Often CQRS is considered an enabler for Event Sourcing"
    - ![](/assets/images/2022-11-25-20-12-58.png)
  - [[t.sd.architecture.event-driven]]

## [[p.hasRelatedSolution]]

- [[soln.castore]]

## [[p.hasRelatedResource]]

- https://medium.com/digitalfrontiers/the-good-the-bad-and-the-ugly-how-to-choose-an-event-store-f1f2a3b70b2d
  - [[p.hasHighlight]]
    - "In order to realize ES, the storage solution aka event store must provide capabilities to read all events using sequential reading, to read all events related to a specific entity, and append events to the event store. Additionally, it must provide transactional capabilities when appending multiple events at once and it must be scalable in terms of the total number of events."
- [[Event Sourcing versus Event Driven Architecture|ar.medium.event-sourcing-versus-event-driven-architecture]]

