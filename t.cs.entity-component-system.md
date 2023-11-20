---
id: EHe5gy8iGwSWZFMwymjar
title: ECS
desc: >-
  runtime-flexible, highly compatible, safe, and easily composable approach to
  software
updated: 1700498015928
created: 1637846686838
---

## Definition

### @sander-mertens

#### Entities & Components

-   An entity is a unique identifier
-   A component can optionally be associated with a plain old datatype
-   A component identifier is an entity
-   An entity can have 0 .. N components
-   A component can be annotated with a role
-   An <entity, component> tuple can have 0 .. N components

#### Systems

-   A system is logic matched with entities based on their components
-   A system is invoked as result of an event
-   A component mutation is an event
-   Computing a simulation frame is an event
-   A frame is divided into N phases
-   Each system is assigned to a phase

### https://forums.coregames.com/t/advanced-code-architecture-for-core-part-2-entity-component-system/3194

- ECS game object is a DDD Entity; an ECS Entity is a DDD Identity; an ECS Component is a DDD Domain Model; and an ECS System is a DDD Service or Aggregate Root. ^h56imtf2ip3n
  - [[c.thought]] i.e., an "ECS game object" is the entity (which is just an ID + list of components) + the functionality and data given by components?

## Implementations

- [[prdct.unity]]
  - [[p.hasDocumentation]] https://docs.unity3d.com/Packages/com.unity.entities@0.1/manual/index.html
- [[prdct.arch]] (C#)
- [[prdct.bitecs]] (Javacript)
  - "Strings are expensive and usually unnecessary to have the ECS handle. Instead, create a mapping of integers to strings, and store the integers in the component data as a reference to a string. This makes string serialization minimal and fast." ^34ftr5hv1m8u
- [[prdct.data-oriented-pyglet]]
- [[prdct.bevy]]

### other implementations

- [[prdct.tick-knock]]
- [[prdct.a-frame]]
  - [[p.hasDocumentation]] https://aframe.io/docs/1.3.0/introduction/entity-component-system.html
  - https://stackoverflow.com/questions/43944365/how-to-do-multiuser-in-a-frame
  - [[p.supports]] [[prdct.networked-aframe]]


## Issues

- https://medium.com/@rdolivo/ecs-for-gamedev-with-typescript-5a1204f594bc
  - Systems are highly dependent on the order in which they are added because their logic works out consistently. Adding new systems between existing ones can be a difficult task.
    - [[p.provokedThoughts]]
      - what if you required every system to be executable in any order. something like [[idempotence|t.cs.idempotence]], but for ordering
  - Changing the content of components can potentially break down many systems.
- "Anything that needs a dynamic ordering of execution is not very intuitive in ECS" 
  - https://forum.unity.com/threads/why-vanilla-ecs-is-not-enough.928287/
    - "Why not put the 'timer' in each component ? Yes you'll need to have one system to update the timer of each type of component having a time... it would be better to have a timmer logic that store the next tick time instead of storing aremaining time that you update every frame. It would allow to make use of the DidChange filtering. Also you could probably define a ITimer interface that your ComponentData would implement and taht should allow you to stream line the timer update systems a bit through generics."
- "One of the biggest "obstacles" (questions) I see is that there will always inevitably be the need to interface with long-running "continuous" processes (maybe because of networking with a much different frequency than the one ECS pipeline of systems is being executed with, maybe because devs will want to use an already written external library spawing own threads without any poll-like API, maybe because there will be a separate event loop system which will not easily integrate with the ECS event loop, etc.)."
  - https://github.com/traffaillac/traffaillac.github.io/issues/1

## Resources

- https://maxwellforbes.com/posts/typescript-ecs-why/
  - [[p.hasHighlight]]
    - "the idea isn’t that there’s a fixed target called a “game engine” that you go out and build, and then you build the game on top of it. For my case at least, the engine is the broader codebase that evolves around the game as you build it."
    - "People like building shit. It’s fun. It’s really fun."
- [[course.gamedev-patterns-ts]]
- https://ajmmertens.medium.com/why-vanilla-ecs-is-not-enough-d7ed4e3bebe5 
  - "Consider creating a “Timer” component that removes a component after N seconds, for example to remove a buff from an entity. An entity can have multiple buffs at the same time, yet I can only add the Timer component once. Solutions to this problem get unwieldy (storing a map in the component value or creating a Timer component for each buff component). This is a serious limitation when applications want to implement generic systems."
  - "Any design language that does not allow me to specify the preconditions for something to work correctly is in my humble opinion flawed."
- https://conferences.oreilly.com/software-architecture/sa-ny/public/schedule/detail/79975.html
- https://gamedev.stackexchange.com/questions/56937/how-to-avoid-blob-systems-in-an-entity-component-system
  - "There's no reason to have fine-grained components like 'movement'. There is no generic movement in your game. You have paddles, whose movement is tightly tied to input or AI (and don't really use velocity, acceleration, restitution, etc.), and you have the ball, which has a well-defined movement algorithm. Just have a PaddleController component and a BouncingBall component or something along those lines. If/when you get a more complicated game then you can worry about having a more generic PhysicsBody component (which in 'real' engines is basically just a link between the game object and whatever internal API object is used by Havok/PhysX/Bullet/Box2D/etc.) that handles a wider variety of situations."
### [[c.resource.list]]

- https://github.com/Chillu1/CSharpECSComparison
- 