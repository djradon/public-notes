---
id: 1j7zJamy6xne6ZZ6Y2PnK
title: Svelto.ECS
desc: ''
updated: 1728865334982
created: 1638152420551
---


- [[c.software.entity-component-system]]
- written-in: [[t.cs.languages.c-sharp]]
- [[p.hasRepository]] https://github.com/sebas77/Svelto.ECS
- [[p.hasCreator]] @sebas77
- [[p.supports]] [[prdct.stride3d]]
- resources:  
  - [[ar.sebaslab.the-quest-for-maintainable-code-and-the-path-to-ecs]]
  - [[ar.sebaslab.whats-new-in-svelto-ecs-3-0]]
  - https://levelup.gitconnected.com/a-beginners-guide-to-svelto-ecs-3-0-with-unity-e9dbc88a2145
  - https://www.sebaslab.com/ecs-abstraction-layers-and-modules-encapsulation/


## Interesting

- In Gamecraft, all the game logic is written with Svelto.ECS, but the physic is simulated with the DOTS ECS physic library with all the performance benefits that come with it.

## Cons

- The main difference compared to any other Archetype-b
- components must be structs, and they cannot hold reference type of any kind. Or you cannot dynamically add or remove component from any entity at runtime. (It means the form/design of an entity is static/immutable.)

## Resources

- 