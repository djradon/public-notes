---
id: zbgt8ydiqczaxg4mn5kutyg
title: Domain Events versus Event Sourcing
desc: ''
updated: 1701453463773
created: 1692393101454
---

- url: https://www.innoq.com/en/blog/2019/01/domain-events-versus-event-sourcing/
- [[c.comparand]] : [[t.cs.sd.event-sourcing]] [[t.cs.sd.ddd.domain-event]]

## Conclusion

- "The events from event sourcing should therefore only be used internally in the corresponding aggregate or in the context of CQRS to build related read models.

Domain events, on the other hand, represent a specific fact or happening that is relevant regardless of the type of persistence strategy for aggregates, for example, for integrating bounded contexts

Event sourcing and domain events can of course be used both at the same time, but should not influence each other. The two concepts are used for different purposes and should therefore not be mixed."

## Highlights

- "the semantics of the fine-grained events from event sourcing is too low-level, both in terms of the event itself and the associated information (the “payload”) [to use those events in other contexts]"

## Thoughts

- interesting point, clarifying example
  - similar: [[Should event objects used in the event-sourcing implementation also be directly used for communication? No! When solely depending on events used in the event-sourcing pattern, a direct dependency is created on the application's internal data.|t.cs.sd.event-sourcing#^vnn4oe20j4t5]]
  - but it seems like at least sometimes, domain events could qualify as event sourcing events, and vice versa
    - e.g. 
      - user clicks "battle axe" -> app constructs intentional-command and submits to approval queue (DM, world-service)"
  - "Domain events are a domain modeling pattern" and "Event sourcing is a data modeling pattern"