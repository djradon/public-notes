---
id: EHe5gy8iGwSWZFMwymjar
title: ECS
desc: >-
  Entity Component Systems are a paradigm of composable object-orientation for
  games and simulations
updated: 1680447269511
created: 1637846686838
---

## [[c.Implementation]]

- [[prdct.Unity]]
  - [[p.hasDocumentation]] https://docs.unity3d.com/Packages/com.unity.entities@0.1/manual/index.html
- [[prdct.a-frame]]
  - [[p.hasDocumentation]] https://aframe.io/docs/1.3.0/introduction/entity-component-system.html
  - https://stackoverflow.com/questions/43944365/how-to-do-multiuser-in-a-frame
  - [[p.supports]] [[prdct.networked-aframe]]
- [[prdct.arch]] (C#)
- [[prdct.bitecs]]
  - "Strings are expensive and usually unnecessary to have the ECS handle. Instead, create a mapping of integers to strings, and store the integers in the component data as a reference to a string. This makes string serialization minimal and fast." ^34ftr5hv1m8u

## [[p.hasCon]]

- https://medium.com/@rdolivo/ecs-for-gamedev-with-typescript-5a1204f594bc
  - Systems are highly dependent on the order in which they are added because their logic works out consistently. Adding new systems between existing ones can be a difficult task.
    - [[p.provokedThoughts]]
      - what if you required every system to be executable in any order. something like [[idempotence|t.cs.idempotence]], but for ordering
  - Changing the content of components can potentially break down many systems.


## [[p.hasRelatedResource]]

- https://maxwellforbes.com/posts/typescript-ecs-why/
  - [[p.hasHighlight]]
    - "the idea isn’t that there’s a fixed target called a “game engine” that you go out and build, and then you build the game on top of it. For my case at least, the engine is the broader codebase that evolves around the game as you build it."
    - "People like building shit. It’s fun. It’s really fun."
- [[course.gamedev-patterns-ts]]

### [[p.hasResourceList]]

- https://github.com/Chillu1/CSharpECSComparison
