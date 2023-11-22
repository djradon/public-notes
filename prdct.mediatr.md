---
id: o93byzx6bc45m3lci3wyh64
title: MediatR
desc: 'request/response, commands, queries, notifications and events, synchronous and async with intelligent dispatching via C# generic variance'
updated: 1694379022145
created: 1694375386102
---

- repo: https://github.com/jbogard/MediatR
- [[p.writtenIn]] [[t.cs.languages.c-sharp]]

## Cons

- **You want event/notification handlers to be run in independently in isolation.** This is where out-of-process messaging comes in. In this case, you might want to look at [NServiceBus](https://particular.net/nservicebus), [Brighter](https://www.goparamore.io/), [MassTransit](https://masstransit-project.com/), [Rebus](https://github.com/rebus-org/Rebus).
  - https://codeopinion.com/why-use-mediatr-3-reasons-why-and-1-reason-not/