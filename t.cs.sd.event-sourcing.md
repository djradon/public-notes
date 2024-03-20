---
id: prbis54rvnvjcg4y74map4h
title: Event Sourcing
desc: >-
  a different way of persisting data where data changes are stored (and read?) as domain events
updated: 1708965971363
created: 1658585055608
---

- replaying events will produce the most up-to-date state of each entity without necessarily knowing how this state was produced in the first place
  - [[p.hasSource]] https://opencredo.com/blogs/events-and-commands-two-faces-of-the-same-coin/
- [[p.couldBeConfusedWith]] 
  - [[t.cs.sd.architecture.cqrs]]
    - "Often CQRS is considered an enabler for Event Sourcing"
    - ![](/assets/images/2022-11-25-20-12-58.png)
    - "commands are external actions while events are internal facts"
      - https://opencredo.com/blogs/events-and-commands-two-faces-of-the-same-coin/
  - [[t.cs.sd.architecture.event-driven]]
    - "Should event objects used in the event-sourcing implementation also be directly used for communication? No! When solely depending on events used in the event-sourcing pattern, a direct dependency is created on the application's internal data. By creating a separate contract that represents the exact data change, a direct dependence on the same models is avoided, and internal data models are not leaked." ^vnn4oe20j4t5
      - [[p.hasSource]] [[Event Sourcing versus Event Driven Architecture|ar.medium.event-sourcing-versus-event-driven-architecture]]
    - "Event sourcing is a more domain specific pattern. It does not care about any other domains and it does not require an event stream. It’s sole purpose is to store its domain state as a sequence of events. These events are stored to record state changes rather than communicating."
      - [[p.hasSource]] https://jgao.io/post/event-sourcing/
        - but also says "any system which uses “event sourcing” as its core mechanics can be seen as also as an event-driven system,"
  - [[t.cs.sd.architecture.command-sourcing]]
  - [[t.cs.sd.architecture.event-streaming]]
    - "Event Sourcing is about durable state stored and read as events, and Event Streaming is about moving events from one place to another."
      - https://event-driven.io/en/event_streaming_is_not_event_sourcing/

## [[p.hasRelatedSolution]]

- [[prdct.castore]]
- [[prdct.eventstoredb]]
- [[prdct.marten]]
- [[prdct.eventide]]

## [[p.hasIssue]]

- "The external systems that your application communicates with are usually not prepared for event sourcing, so you should be careful when you replay your events... To solve this challenge, you should handle replays in your communication layers!"
  - [[p.hasSource]] [[Event Sourcing with Examples Node.js at Scale|ar.risingstack.event-sourcing-with-examples-node-js-at-scale]]


## Resources

- https://medium.com/digitalfrontiers/the-good-the-bad-and-the-ugly-how-to-choose-an-event-store-f1f2a3b70b2d
  - [[p.hasHighlight]]
    - "In order to realize ES, the storage solution aka event store must provide capabilities to read all events using sequential reading, to read all events related to a specific entity, and append events to the event store. Additionally, it must provide transactional capabilities when appending multiple events at once and it must be scalable in terms of the total number of events."
- [[Event Sourcing versus Event Driven Architecture|ar.medium.event-sourcing-versus-event-driven-architecture]]
- [[ar.event-driven.type-script-node-js-event-sourcing]]
- [[ar.domaincentric.event-sourcing-projections]]
- [[ar.event-driven.projections-and-read-models-in-event-driven-architecture]]
- https://github.com/oskardudycz/EventSourcing.NodeJS
- https://stackoverflow.com/questions/67356709/event-sourcing-and-domain-event
- https://stackoverflow.com/questions/71083541/event-sourcing-vs-event-driven-architecture-difference
- https://medium.com/andamp/event-sourcing-with-spring-modulith-2b35b0569dbb
  - mentions: [[prdct.spring.modulith]]