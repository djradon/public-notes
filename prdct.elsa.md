---
id: exxdl5e1tjctca2adjhzxmo
title: Elsa
desc: 'open source .NET Standard workflows library that lets you define workflows as C#, visual designer, or json'
updated: 1707692527210
created: 1680579451412
---

- [[p.instanceOf]] [[c.software.workflow]]
- repo: https://github.com/elsa-workflows/elsa-core

## Features

-   Support for both short-running and long-running workflows.
-   A web-based drag & drop designer with support for custom activities.
-   Native support for activity composition, including activities like `Sequence`, `Flowchart`, and `ForEach`.
-   Parallel execution of activities.
-   Built-in activities for common scenarios, such as sending emails, making HTTP calls, scheduling tasks, sending and receiving messages, and more.
-   Workflow versioning and migration via API.
-   Easy integration with external applications via HTTP, message queues, and more.
-   Actor model for increased workflow throughput. (used [[prdct.proto-actor]])
-   Dynamic expressions with support for C#, JavaScript, Python, and Liquid.
-   Alterations API: Modify existing workflow instances at runtime.
-   activities can schedule other activities
-   Service Bus Broker: [[prdct.rebus]] for sending messages via service bus brokers. Out of the box, it uses a memory provider.
-   Distributed Lock Provider: filesystem, [[prdct.redis]], [[prdct.sql-server]], Azure
-   Distributed Temporal Services: A temporal service provides functionality to schedule a workflow to execute at a specific time and/or on a recurring interval. Elsa uses these services to implement the Timer, Cron and StartAt activities; supports [[prdct.quartz-net]] and [[prdct.hangfire]]

## Cons

- The designer is not yet fully embeddable in other applications; this feature is planned for a future release.
- The designer currently only supports Flowchart activities. Support for Sequence and StateMachine activities is planned for a future release.
- UI input validation is not yet implemented.

## Resources

- https://sipkeschoorstra.medium.com/part-7-of-building-workflow-driven-net-applications-with-elsa-2-e369e7784555
- https://sipkeschoorstra.medium.com/elsa-3-0-2b341e7cbfa7