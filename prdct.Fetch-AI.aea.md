---
id: X5Ct3klCWxDuWjI4ARtGE
title: aea
desc: autonomous economic agent
updated: 1698611100465
created: 1637853714937
---

## Terms

### Skills

- self-contained capabilities that implement business logic to deliver economic value for the AEA
- A skill encapsulates implementations of the three abstract base classes `Handler`, `Behaviour`, `Model`, and is closely related with the abstract base class `Task`:
  -   [`Handler`](https://docs.fetch.ai/aea-framework-documentation/protocol-generator/#how-to-run../api/skills/base#handler-objects): each skill has zero, one or more `Handler` objects, each responsible for the registered messaging protocol. Handlers implement AEAs' **reactive** behaviour. If the AEA understands the protocol referenced in a received `Envelope`, the `Handler` reacts appropriately to the corresponding message. Each `Handler` is responsible for only one protocol. A `Handler` is also capable of dealing with internal messages (see next section).
  -   [`Behaviour`](https://docs.fetch.ai/aea-framework-documentation/protocol-generator/#how-to-run../api/skills/base#behaviour-objects): zero, one or more `Behaviours` encapsulate actions which further the AEAs goal and are initiated by internals of the AEA, rather than external events. Behaviours implement AEAs' **pro-activeness**. The framework provides a number of [abstract base classes](https://docs.fetch.ai/aea-framework-documentation/protocol-generator/#how-to-run../api/skills/behaviours) implementing different types of behaviours (e.g. cyclic/one-shot/finite-state-machine/etc.).
  -   [`Model`](https://docs.fetch.ai/aea-framework-documentation/protocol-generator/#how-to-run../api/skills/base#model-objects): zero, one or more `Models` that inherit from the `Model` class. `Models` encapsulate custom objects which are made accessible to any part of a skill via the `SkillContext`.
  -   [`Task`](https://docs.fetch.ai/aea-framework-documentation/protocol-generator/#how-to-run../api/skills/tasks#task-objects): zero, one or more `Tasks` encapsulate background work internal to the AEA. `Task` differs from the other three in that it is not a part of skills, but `Task`s are declared in or from skills if a packaging approach for AEA creation is used.

- [[p.hasRepository]] https://github.com/fetchai/agents-aea
