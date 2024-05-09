---
id: 08k9bzf078nrt71hp1rxaao
title: Orchestration
desc: still need a component that is aware of the entire workflow
updated: 1715286462624
created: 1680909338629
---

![](/assets/images/2023-10-06-14-20-41.png)
- related: [[t.cs.sd.architecture.choreography]]
  - but they're not opposites; it's kinda a false distinction. if systems determine their behavior based on messages, and the messages are "do this by then", you're getting orchestrated

- "a dedicated workflow service acts as the central orchestrator, coordinating the various microservices involved in a business process. This service initiates the process flow, manages the sequence of events and service invocations, and handles errors or retries as needed. The orchestration pattern simplifies the development and maintenance of complex event-driven processes while providing better observability and control compared to the choreography pattern." ^21ydosqb6dt1


## Implementations

- [[prdct.workflow-core]]
- [[prdct.prefect]]
- [[prdct.temporal]]
- [[prdct.infinitic]]

## Resources

- https://dzone.com/articles/orchestration-pattern-managing-distributed-transac
  - "We have designed an appropriate architecture where all services operate within their bounded context. However, we still need a component that is aware of the entire business workflow."

## References

- https://gillesbarbier.medium.com/an-easy-path-from-api-based-microservices-to-an-event-driven-architecture-for-improved-reliability-00d7d0bc3828