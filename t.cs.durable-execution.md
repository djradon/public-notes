---
id: a8xiu1yko8xakp9omp56mq7
title: Durable Execution
desc: ''
updated: 1705954337469
created: 1705954291505
---

## Story

- After Amazon (one of the first large adopters of microservices) decided that using message queues to communicate between services was not the way to go (hear the story first-hand [here](https://www.youtube.com/watch?v=wIpz4ioK0gI)), they started using orchestration. And once they realized defining orchestration logic in YAML/JSON wasn’t a good developer experience, they created [AWS Simple Workfow Service](https://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-welcome.html) to define logic in code. This technique of backing code by an orchestration engine is called durable execution, and it spread to [Azure Durable Functions](https://learn.microsoft.com/en-us/azure/azure-functions/durable/durable-functions-overview?tabs=csharp-inproc), [Cadence](https://cadenceworkflow.io/) (used at Uber for [\> 1,000 services](https://www.uber.com/blog/announcing-cadence/)), and [Temporal](https://temporal.io/) (used by Stripe, Netflix, Datadog, Snap, Coinbase, and many more).

## References

- https://temporal.io/blog/time-travel-debugging-production-code