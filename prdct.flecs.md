---
id: 7gdppz90ynqtxqlw29ln9jj
title: Flecs
desc: ''
updated: 1712470421539
created: 1686260852478
---


- [[c.software.entity-component-system]]
- repo: https://github.com/SanderMertens/flecs
- written-in: #c #c++ 
- author: @sander-mertens
- supports: c# via [[prdct.flecs.flecs-cs]]
- inspiration: prolog

## FAQ

- Can I use Flecs without using systems?
  - You can! Systems are an optional addon that can be disabled. You can build applications that just use Flecs queries.

## Features

- World cell partitioning
- "Flecs introduced an extremely powerful innovation to ECS - the concept of an entity relationship. You can relate one entity to another via a relationship containing metadata. For example, a player entity can be related to a character entity via a Controls relationship. One entity could follow another entity via a Follow relationship. This allows you to conveniently express patterns that would not be possible only via components. When I read about this idea I immediately borrowed it for my own ECS library and it was like a missing link that let me get rid of all kinds of awkwardly structured patterns that I had used before.

Beyond that, the main innovation of Flecs is that it’s structured like a database, to allow you to perform complex data queries on the structure of the world. It has all kinds of neat design tricks, like the fact that every component type is actually also an entity itself. This stuff is like catnip for a certain type of programmer. Leibniz himself would weep at its purity."
  - https://moonside.games/posts/archetypal-ecs-considered-harmful/

## Learning Resource

- ![FLECS overview](https://github.com/SanderMertens/flecs/raw/master/docs/img/flecs-quickstart-overview.png)

