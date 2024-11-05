---
id: YEENs52Vldkdwe2jkkRpe
title: Stride3d
desc: Open-source C# Game Engine
updated: 1730843232317
created: 1637846271510
---

- [[c.software.game-engine]]
- aka: Xenko
- url: https://www.stride3d.net/
- repo: https://github.com/stride3d/stride
- [[c.comparable]] [[prdct.unity]] [[prdct.monogame]]
- written-in: c#
- [[p.usedBy]] [[prdct.vvvv]]

## Features

- [[t.cs.entity-component-system]]
- [[p.isTopicOfDiscussion]] https://community.monogame.net/t/did-you-know-that-stride-is-basically-monogame-with-a-3d-editor/12250/4 

## Cons

- no game-server / server-authoritative out of the box.
  - "Stride works fine for building the client, but you will want a specialized and dedicated server on the back end."
    - https://forums.stride3d.net/t/mmorpg-networking-noob-questions/2270/2
- no web support
  https://github.com/stride3d/stride/issues/70

## Examples

- https://github.com/xen2/Xenko.ClientServerSample #dead

## [[p.vs]] [[prdct.godot]]

- "Godot is just older and more established, but Stride has a better render engine, software architecture and is a pure .NET project. So the engine and the scripting use the same technology. Godot has a C++ core and only "interprets" the scripting languages, which is conceptually quite different."
  - https://news.ycombinator.com/item?id=32300785

## Resources

- https://www.sebaslab.com/svelto-miniexample-7-stride-engine-demo/
  - [[p.isRelated]] [[prdct.svelto-ecs]]

## References

- [Code-Only Approach](https://github.com/stride3d/stride/issues/1295)
- [Stride3D - Life beyond Unity?](https://www.i-programmer.info/news/144-graphics-and-games/16120-stride3d-life-beyond-unity.html)