---
id: 1e9aid4vcw7v1perfk5e3bn
title: Spork
desc: 'Spoon’s Operations Research Kit'
updated: 1715182748877
created: 1708543959199
---

- [[c.software.simulation-framework.discrete-event]]
 [[c.software.simulation-framework]] [[c.Software.Entity-Component-System]]
- [[t.cs.sd.literate-programming]] [[t.cs.immutability]]
- repo: https://github.com/joinr/spork

## Description

- SPORK.sim presents a significant departure from traditional Discrete Event Simulations, since the architecture embraces functional programming and persistent data structures wholly, rather than focusing on mutation.

## Features

-   building the simulation transition functions (or step functions) as a composition of smaller functions
    -   (as opposed to OOP-based classes or imperative mutation)
-   Optionally persistent, lazily computed stream of simulation history
-   a database layer based on the Component-Entity-System paradigm
-   Maintains the ability to have a classic observable/observer simulation model without sacrificing functional purity.
    -   Where convenient (i.e. for logging, visualization, other side-effects).
-   Event-step (i.e. variable-width time-step) simulation.
-   High-level transforms on the simulation history.
    -   Familiar idioms like map, filter, reduce work out of the box, since history is merely a time-indexed stream of simulation contexts.
    -   Allows for precise reasoning about causality, tracing, debugging, etc.
-   Entity behaviors based on Behavior Trees, but can be as simple as a 2-line function.

## References

- https://www.reddit.com/r/Clojure/comments/15b81ch/xx_clojure_entity_component_system_working_on/