---
id: x13bm4xhdrln614wamciszm
title: Proto.Actor
desc: ''
updated: 1698188017647
created: 1693696915552
---

- [[c.Software.Actor-Framework]]
- #url https://proto.actor
- [[c.Software.Distributed-Systems-Runtime]]
- [[p.similarTo]] [[prdct.orleans]]
- [[c.Implementation]]
  -  https://github.com/asynkron/protoactor-go #go 
  -  https://github.com/asynkron/protoactor-dotnet #c-sharp
  -  https://github.com/asynkron/protoactor-kotlin #kotlin

## [[c.Feature]]

- migration -> local affinity https://proto.actor/docs/local-affinity/
- "Proto.Actor uses Protobuf for serialization, a decision that vastly simplifies the way Proto.Actor works. Message based systems should be about passing information, not passing complex OOP object graphs or code." 
- Proto.Persistence module allows an actor to recover its state when it is started and supports three modes of operation:
  - Event Sourcing
  - Snapshotting
  - Event Sourcing with Snapshotting 
    - snapshotting becomes a performance optimisation for cases when you have large numbers of events to replay to rebuild the state of your actor


### Behaviors

- Actors can change their behavior at any time. This is achieved through the Behavior class included with the core Proto.Actor library.

## [[c.Resource]]

- https://proto.actor/docs/what-is-protoactor/

### [[c.Resource.Learning]]

- https://proto.actor/docs/bootcamp/
