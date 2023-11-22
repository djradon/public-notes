---
id: 97klrfqph1k3m77oi8xmdaz
title: Building Games in Ecs with Entity Relationships
desc: relationships are encoded as component ids
updated: 1686260851853
created: 1686246848888
---

- url: https://ajmmertens.medium.com/building-games-in-ecs-with-entity-relationships-657275ba2c6c
- [[c.topic]] [[prdct.flecs]]

- "player_2 is a regular entity, which means we can’t know its identifier before running the game. This is different from a regular component, which (in most ECS frameworks) has to be known at compile time. This brings us to the second defining feature of relationships: Relationship pairs can contain regular entities"
- "Queries are treated as a list of nodes. Each node implements a function that can return either true or false. When a node returns true, the query moves on to the next node. When a node returns false, it goes back one node. These kinds of functions are called predicates, and this evaluation process is called backtracking."
  - "ECS queries on the other hand already use fast data structures for finding entities, and with the few tweaks we discussed here they can be extended to general-purpose query engines for graphs."