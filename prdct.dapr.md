---
id: f33o5k09ibm1yybd1s62a7g
title: Dapr
desc: 'portable, event-driven, runtime for building distributed applications'
updated: 1690181907236
created: 1688397077910
---

- #url https://dapr.io
- #repo https://github.com/dapr
- [[c.Documentation]] https://docs.dapr.io

## [[p.supports]]

- [[prdct.nats.jetstream]] (alpha for state, )
- [[prdct.Postgres]]

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


## [[c.Resource]]

- https://www.reddit.com/r/dotnet/comments/13t3tsf/is_dapr_actually_used_by_anyone/
  - "just a set of APIs hosted in the sidecar that you can opt-in to calling if you want some particular feature such as using Pubsub or acquiring a distributed lock. It does not enforce any particular way for you to structure your application code"

[[c.Resource.Learning]]

- https://learn.microsoft.com/en-us/dotnet/architecture/dapr-for-net-developers/?ref=daveabrock.com
- [[book.practical-microservices-with-dapr-and-dotnet]]                                 