---
id: x13bm4xhdrln614wamciszm
title: Proto.Actor
desc: ''
updated: 1698262670488
created: 1693696915552
---

- [[c.software.actor-framework]]
- #url https://proto.actor
- [[c.software.distributed-systems-runtime]]
- [[p.similarTo]] [[prdct.orleans]]
- [[c.implementation]]
  -  https://github.com/asynkron/protoactor-go #go 
  -  https://github.com/asynkron/protoactor-dotnet #c-sharp
  -  https://github.com/asynkron/protoactor-kotlin #kotlin

## Features

- migration -> local affinity https://proto.actor/docs/local-affinity/
- "Proto.Actor uses Protobuf for serialization, a decision that vastly simplifies the way Proto.Actor works. Message based systems should be about passing information, not passing complex OOP object graphs or code." 
- Proto.Persistence module allows an actor to recover its state when it is started and supports three modes of operation:
  - Event Sourcing
  - Snapshotting
  - Event Sourcing with Snapshotting 
    - snapshotting becomes a performance optimisation for cases when you have large numbers of events to replay to rebuild the state of your actor


### Behaviors

- Actors can change their behavior at any time. This is achieved through the Behavior class included with the core Proto.Actor library.

## Resources

- https://proto.actor/docs/what-is-protoactor/

### Learning Resource

- https://proto.actor/docs/bootcamp/
