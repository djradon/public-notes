---
id: ehflhupgftjncjisnmcxyzy
title: Event Driven Architecture
desc: 'Event-driven architecture uses events to communicate notable data changes between service boundaries'
updated: 1672341710658
created: 1669463161648
---

## [[p.hasRelatedResource]] 

- https://cloud.google.com/eventarc/docs/event-driven-architectures
- https://medium.com/geekculture/event-sourcing-versus-event-driven-architecture-753aa5a5d0f6
  - [[p.hasHighlight]]  ^973t2iqz9www
    - "the event is used as a data contract to communicate the information" 
    - "The publisher and the consumer must have a common understanding of the message that gets shared."
    - "Should event objects used in the event-sourcing implementation also be directly used for communication? No! When solely depending on events used in the event-sourcing pattern, a direct dependency is created on the application's internal data. By creating a separate contract that represents the exact data change, a direct dependence on the same models is avoided, and internal data models are not leaked."

### [[p.hasLearningResource]]

- [[ar.medium.edge-coders.understanding-node-js-event-driven-architecture]]