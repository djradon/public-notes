---
id: f33o5k09ibm1yybd1s62a7g
title: Dapr
desc: 'portable, event-driven, runtime for building distributed applications'
updated: 1707845604682
created: 1688397077910
---

- [[c.software.distributed-systems-runtime]] [[c.software.actor-framework]]
- url: https://dapr.io
- repo: https://github.com/dapr
- [[c.documentation]] https://docs.dapr.io

## [[p.supports]]

- c# #python javascript java #go #php #c++ #rust (see https://docs.dapr.io/developing-applications/sdks/)
- [[prdct.nats.jetstream]] (alpha for state)
- [[prdct.postgres]]
- #python: [[prdct.grpc]] [[prdct.fastapi]] [[prdct.flask]]
- [[prdct.mqtt]]

## [[p.hasNoSupportFor]]

- [[t.cs.languages.f-sharp]] or any functional language

## Features

-   **Client**: The Dapr client allows you to invoke Dapr building block APIs and perform each building block’s actions
-   **Server extensions**: The Dapr service extensions allow you to create services that can be invoked by other services and subscribe to topics
-   **Actor**: The Dapr Actor SDK allows you to build virtual actors with methods, state, timers, and persistent reminders
-   **Workflow**: Dapr Workflow makes it easy for you to write long running business logic and integrations in a reliable way

### State Store (Hot Data)

- key-value only? can work with relational dbs, but not designed for all yer customer data (https://youtu.be/0y7ne6teHT4)
  - [share state across applications](https://docs.dapr.io/developing-applications/building-blocks/state-management/howto-share-state/)

### Bindings

- input bindings trigger endpoint methods
- dapr executes operations on external systems via output bindings

## Use Cases

- "You want to work with single-threaded objects that do not require significant interaction from external components, including querying state across a set of actors."

## [[c.faq]]

- "What is the relationship between Dapr, Orleans and Service Fabric Reliable Actors?"
  - Dapr's actor framework is  similar to Orleans
- "Differences between Dapr and an actor framework"
  - "actors can be called from any language. This allows actors written in one language to invoke actors written in a different language... Currently .NET, Java, Go and Python SDK have actor frameworks."
  -  Dapr is a comprehensive microservice sidecar that does lots of different things.
    - https://www.reddit.com/r/dotnet/comments/13t3tsf/is_dapr_actually_used_by_anyone/ 
      - "if you have a product that aspires to be vendor agnostic, it might help"

## Issues

-"You cannot dynamically add new programmatic subscriptions, only add new ones at compile time"
  - https://docs.dapr.io/developing-applications/building-blocks/pubsub/subscription-methods/
  - and presumably the declarative subscriptions too

## [[c.notes]]

- "Redis does not support transaction rollbacks and should not be used in production as an actor state store."
- the Dapr SDK for Java builds upon Project Reactor, all methods are asynchronous. This means they return a Mono<T> or a Flux<T>, respectively a single item or a stream of items somewhere in the future. Since both a Mono<T> and a Flux<T> are “cold”, you have to “subscribe” on them. By subscribing, you tell the code that will produce the items that you are ready to process the items that they will produce. One of the ways to do this is by invoking .block() on the Mono<T> or Flux<T>.
  - https://maarten.mulders.it/2022/01/the-dapr-sdk-for-java-pubsub-distributed-tracing/


## Examples

- https://github.com/dotnet-architecture/eShopOnDapr #showcase
- [[prdct.dapr-traffic-control]]
- https://github.com/kimcuhoang/dapr-tye-simple-microservices
- https://github.com/thangchung/practical-dapr #dead
- https://github.com/vietnam-devs/coolstore-microservices "Minimal Clean Architecture with DDD-lite, CQRS-lite, and just enough Cloud-native patterns apply on the simple eCommerce"
- https://github.com/benc-uk/dapr-store #go
- https://github.com/sjefvanleeuwen/showcase
  - [[p.builtOn]] [[prdct.zeebe]] [[prdct.camunda.modeler]]
- https://github.com/thangchung/coffeeshop-on-dapr
- https://github.com/thangchung/clean-architecture-dotnet

## Resources

- https://www.reddit.com/r/dotnet/comments/13t3tsf/is_dapr_actually_used_by_anyone/
  - "just a set of APIs hosted in the sidecar that you can opt-in to calling if you want some particular feature such as using Pubsub or acquiring a distributed lock. It does not enforce any particular way for you to structure your application code"
- https://raw.githubusercontent.com/dotnet-architecture/eBooks/main/current/dapr-for-net-developers/Dapr-for-NET-Developers.pdf
- https://learning.oreilly.com/library/view/practical-microservices-with/9781803248127/B18620_01.xhtml#_idParaDest-31
- https://blog.dapr.io/posts/2021/01/26/observing-dapr-applications-with-new-relic-one/
- https://dev.to/aaronblondeau/virtual-actors-dapr-vs-orleans-30f0
 - https://medium.com/event-driven-utopia/5-reasons-why-you-should-use-microsoft-dapr-to-build-event-driven-microservices-cb2202c579a0
- https://itnext.io/dapr-vs-envoy-when-to-use-what-6c2ac3caaed2
- https://www.daveabrock.com/2021/04/29/meet-dapr/
- [-  ] https://medium.com/codex/event-driven-programming-with-dapr-db96ac855a2d

### Learning Resources

- https://learn.microsoft.com/en-us/dotnet/architecture/dapr-for-net-developers/
- [[book.practical-microservices-with-dapr-and-dotnet]]                            - https://www.freshbrewed.science/dapr-getting-started/index.html
  - has a node service and python client