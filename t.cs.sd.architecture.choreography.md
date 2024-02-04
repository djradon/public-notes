---
id: 3tczusavbqsr54n2gp88jl1
title: Choreography
desc: ''
updated: 1696627571764
created: 1689742269151
---

![](/assets/images/2023-10-06-14-21-19.png)

- harder to reason about, because reactions can happen anywhere in the system

## vs [[t.cs.sd.architecture.orchestration]]

- "Orchestration is a centralized approach to making all control decisions about interactions between services. Here a central orchestrator service coordinates all of the other services that execute a business transaction or workflow. By contrast, a choreography is a decentralized approach to coordinating this workflow, where each service determines its own behavior based on the messages it receives from other services."


## Implementations

- [[prdct.masstransit]] c#

## Resources

- https://www.infoworld.com/article/3687638/orchestration-and-choreography-in-net-microservices.html