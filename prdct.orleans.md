---
id: utmsc3ewjjs81fsgw9q48kf
title: Orleans
desc: ''
updated: 1692390207430
created: 1670267305306
---

- #summary https://learn.microsoft.com/en-us/dotnet/orleans/overview
  - [[p.hasHighlight]]
    - based on [[t.cs.actors]]
- [[p.hasConcept]] 
  - [[t.cs.actors.virtual]]
    - [[p.represented]] as [[t.cs.actors.grain]]
  - [[prdct.orleans.silo]]

## [[c.UseCase]]

Orleans should be considered when:

-   Significant number (hundreds, millions, billions, and even trillions) of loosely coupled entities. To put the number in perspective, Orleans can easily create a grain for every person on Earth in a small cluster, so long as a subset of that total number is active at any point in time.
    -   Examples: user profiles, purchase orders, application/game sessions, stocks.
-   Entities are small enough to be single-threaded.
    -   Example: Determine if the stock should be purchased based on the current price.
-   Workload is interactive.
    -   Example: request-response, start/monitor/complete.
-   More than one server is expected or may be required.
    -   Orleans runs on a cluster that is expanded by adding servers to expand the cluster.
-   Global coordination is not needed or on a smaller scale between a few entities at a time.
    -   Scalability and performance of execution are achieved by parallelizing and distributing a large number of mostly independent tasks with no single point of synchronization.

## [[p.hasLearningResource]]

- [Adventure game sample project | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/orleans/tutorials-and-samples/adventure)
- [stack overflow: Orleans slow with minimalistic use case](https://stackoverflow.com/questions/74310628/orleans-slow-with-minimalistic-use-case)
- [Building a realtime server backend using the Orleans Actor system, Dotnet Core and Server-side Redux](https://medium.com/@MaartenSikkema/using-dotnet-core-orleans-redux-and-websockets-to-build-a-scalable-realtime-back-end-cd0b65ec6b4d)