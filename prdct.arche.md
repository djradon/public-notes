---
id: o82gjydx1odbs49bmg4m6ar
title: Arche
desc: ''
updated: 1706899536719
created: 1706895772664
---

- repo: https://github.com/mlange-42/arche
- uses: [[prdct.pixel]]
- written_in: go

## Features

-   Simple [core API](https://pkg.go.dev/github.com/mlange-42/arche/ecs). See the [API docs](https://pkg.go.dev/github.com/mlange-42/arche).
-   Optional logic [filter](https://pkg.go.dev/github.com/mlange-42/arche/filter) and type-safe [generic](https://pkg.go.dev/github.com/mlange-42/arche/generic) API.
-   Entity relations as first-class feature. See [Architecture](https://github.com/mlange-42/arche/blob/main/ARCHITECTURE.md#entity-relations).
-   World serialization and deserialization with [arche-serde](https://github.com/mlange-42/arche-serde).
-   No systems. Just queries. Use your own structure (or the [Tools](https://github.com/mlange-42/arche?tab=readme-ov-file#tools)).
    -   similar to [[prdct.bitecs]]?
-   No dependencies. Except for unit tests ([100% coverage](https://coveralls.io/github/mlange-42/arche)).
-   Probably the fastest Go ECS out there. See the [Benchmarks](https://github.com/mlange-42/arche?tab=readme-ov-file#benchmarks).
-   

## Interesting

- Arche is designed for the development of scientific, individual-based models rather than for game development. This motivates some design decisions, with an emphasis on simplicity, safety and performance. Nevertheless, Arche can also be used for game development.

## Cons

- The number of component types per World is limited to 256. This is mainly a performance decision.