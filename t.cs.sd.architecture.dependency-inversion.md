---
id: m9zi7wqwqz525kas63hfc7l
title: Dependency Inversion
desc: >-
  the Flow of Control Dependency goes in one direction between two projects or
  dlls, but the Source Code Dependency goes in the other direction
updated: 1690264792193
created: 1690261969574
---

- Flow of Control Dependency — when you are debugging code and the line of execution goes from one project into another project or dll.
- Source Code Dependency — where one project references another project or dll.
- We invert a Source Code Dependency when we identify that the rate of change of a project is more than the project that depends on it.
- an Abstraction is an interface and a Detail is an implementation.

## [[c.Conclusion]]

- For Flow of Control Dependencies, inject dependencies as interfaces, or abstractions.
- Ensure the abstractions, or interfaces, are defined in a higher level module and implemented in a lower level module to ensure the Source Code Dependency is Inverted.

## [[c.Resource]]

- 1: https://medium.com/codex/the-difference-between-dependency-inversion-and-dependency-injection-15935337ca1b
