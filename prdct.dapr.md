---
id: f33o5k09ibm1yybd1s62a7g
title: Dapr
desc: 'portable, event-driven, runtime for building distributed applications'
updated: 1697168627643
created: 1688397077910
---

- [[c.Software.Distributed-Systems-Runtime]]
- #url https://dapr.io
- #repo https://github.com/dapr
- [[c.Documentation]] https://docs.dapr.io

## [[p.supports]]

- #c-sharp #python #javascript #java #go #php #c++ #rust (see https://docs.dapr.io/developing-applications/sdks/)
- [[prdct.nats.jetstream]] (alpha for state)
- [[prdct.Postgres]]
- #python: [[prdct.grpc]] [[prdct.fastapi]] [[prdct.flask]]
- [[prdct.mqtt]]

## [[p.hasNoSupportFor]]

- #f-sharp or any functional language

## [[c.Feature]]

### State Store (Hot Data)

- key-value only? can work with relational dbs, but not designed for all yer customer data (https://youtu.be/0y7ne6teHT4)
  - [share state across applications](https://docs.dapr.io/developing-applications/building-blocks/state-management/howto-share-state/)

## [[c.UseCase]]

- "You want to work with single-threaded objects that do not require significant interaction from external components, including querying state across a set of actors."

## [[c.FAQ]]

- "What is the relationship between Dapr, Orleans and Service Fabric Reliable Actors?"
  - Dapr's actor framework is  similar to Orleans
- "Differences between Dapr and an actor framework"
  - "actors can be called from any language. This allows actors written in one language to invoke actors written in a different language... Currently .NET, Java, Go and Python SDK have actor frameworks."
  -  Dapr is a comprehensive microservice sidecar that does lots of different things.
    - https://www.reddit.com/r/dotnet/comments/13t3tsf/is_dapr_actually_used_by_anyone/ 
      - "if you have a product that aspires to be vendor agnostic, it might help"

## [[c.Example]]

- https://github.com/kimcuhoang/dapr-tye-simple-microservices
- https://github.com/thangchung/practical-dapr #dead
- https://github.com/vietnam-devs/coolstore-microservices "Minimal Clean Architecture with DDD-lite, CQRS-lite, and just enough Cloud-native patterns apply on the simple eCommerce"
- https://github.com/benc-uk/dapr-store #go


## [[c.Resource]]

- https://www.reddit.com/r/dotnet/comments/13t3tsf/is_dapr_actually_used_by_anyone/
  - "just a set of APIs hosted in the sidecar that you can opt-in to calling if you want some particular feature such as using Pubsub or acquiring a distributed lock. It does not enforce any particular way for you to structure your application code"
- https://raw.githubusercontent.com/dotnet-architecture/eBooks/main/current/dapr-for-net-developers/Dapr-for-NET-Developers.pdf
- https://learning.oreilly.com/library/view/practical-microservices-with/9781803248127/B18620_01.xhtml#_idParaDest-31
- https://blog.dapr.io/posts/2021/01/26/observing-dapr-applications-with-new-relic-one/
- https://dev.to/aaronblondeau/virtual-actors-dapr-vs-orleans-30f0
 - https://medium.com/event-driven-utopia/5-reasons-why-you-should-use-microsoft-dapr-to-build-event-driven-microservices-cb2202c579a0
- https://itnext.io/dapr-vs-envoy-when-to-use-what-6c2ac3caaed2
- 
[[c.Resource.Learning]]

- https://learn.microsoft.com/en-us/dotnet/architecture/dapr-for-net-developers/
- [[book.practical-microservices-with-dapr-and-dotnet]]                            - https://www.freshbrewed.science/dapr-getting-started/index.html
  - has a node service and python client