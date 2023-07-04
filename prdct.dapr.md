---
id: f33o5k09ibm1yybd1s62a7g
title: Dapr
desc: 'portable, event-driven, runtime for building distributed applications'
updated: 1688445738107
created: 1688397077910
---

- #url https://dapr.io
- #repo https://github.com/dapr
- [[c.Documentation]] https://docs.dapr.io

## [[p.supports]]

- [[prdct.nats.jetstream]] (alpha)
- [[prdct.Postgres]]

## [[c.UseCase]]

- "You want to work with single-threaded objects that do not require significant interaction from external components, including querying state across a set of actors."

## [[c.FAQ]]

- "What is the relationship between Dapr, Orleans and Service Fabric Reliable Actors?"
  - Dapr's actor framework is  similar to Orleans
- "Differences between Dapr and an actor framework"
  - "actors can be called from any language. This allows actors written in one language to invoke actors written in a different language... Currently .NET, Java, Go and Python SDK have actor frameworks."