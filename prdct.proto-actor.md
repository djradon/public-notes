---
id: x13bm4xhdrln614wamciszm
title: Proto.Actor
desc: ''
updated: 1707691629030
created: 1693696915552
---

- [[c.software.distributed-systems-runtime]] [[c.software.actor-framework]]
- url: https://proto.actor
- [[p.similarTo]] [[prdct.orleans]] [[prdct.akka-net]] 
- [[c.implementation]]
  -  https://github.com/asynkron/protoactor-go #go 
  -  https://github.com/asynkron/protoactor-dotnet c#
  -  https://github.com/asynkron/protoactor-kotlin #kotlin
- uses: gRPC with protobuf

## Features

- migration -> local affinity https://proto.actor/docs/local-affinity/
- "Proto.Actor uses Protobuf for serialization, a decision that vastly simplifies the way Proto.Actor works. Message based systems should be about passing information, not passing complex OOP object graphs or code." 
- "Proto.Actor also uses gRPC, leveraging HTTP/2 streams for network communication."
- Proto.Persistence module allows an actor to recover its state when it is started and supports three modes of operation:
  - Event Sourcing
  - Snapshotting
  - Event Sourcing with Snapshotting 
    - snapshotting becomes a performance optimisation for cases when you have large numbers of events to replay to rebuild the state of your actor
- "Just like everything else in Proto.Actor where we have re-used proven technologies such as Protobuf and gRPC, we do the same for clustering, we do not reinvent the wheel and create our own cluster mechanics. Instead, we leverage proven technologies such as Consul, ETCD or Kubernetes to power our Cluster member management."

### Behaviors

- Actors can change their behavior at any time. This is achieved through the Behavior class included with the core Proto.Actor library.

## Thoughts

- "Message based systems should be about passing information, not passing complex OOP object graphs or code." [1]

## Examples

- https://github.com/asynkron/realtimemap-dotnet

## Resources

- https://proto.actor/docs/what-is-protoactor/

### Learning Resource

- https://proto.actor/docs/bootcamp/

## References

- [1]: https://proto.actor/docs/what-is-protoactor/