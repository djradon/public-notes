---
id: 7hux6zzyxccdbhl5isny3je
title: Dapr Actors
desc: ''
updated: 1709825073585
created: 1709824260644
---

- hosted_by: @marc-duiker
- example: [[prdct.dapr-actor-demos]]

- use workflows instead for long-running processes
- turn-based access model
- idea: maybe the actor is the companion/sidecar to the agent 
- virtual actor: not tied to in-memory representation
- timers are stateless (lost after actor deactivation)
- reminders are stateful (persists after deactivation, will rehydrate actor)

## Actors API

- 