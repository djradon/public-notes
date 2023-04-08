---
id: py9r8c41at3tcwrquyroj10
title: Projection
desc: ''
updated: 1675207472910
created: 1675206736367
---

## [[c.Claim]]

###  projection implementations tend to have a couple of moving parts

- A repository that allows to find or store a state
- A projector that has event handlers that know how to update or create a state

### the only difference between [[t.cs.sd.event-sourcing.projection]] and [[t.cs.sd.ddd.aggregate]] is intent

- Internal aggregate state exists so that we can make a decision if a command should be processed, and if yes then what are the new events that should be persisted (so the C from CQRS). 
- On the other hand projections always answer a question about the facts that already happened to the system (the Q part of CQRS).

## [[c.Resource]]

- [[ar.domaincentric.event-sourcing-projections]]