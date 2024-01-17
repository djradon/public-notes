---
id: bSLil5qIzVfZquxwKn40B
title: Colyseus
desc: >-
  multiplayer framework and cloud solution with multi-client support, including
  unity
updated: 1705515902679
created: 1642897812921
---

- [[c.Software.Game-Framework]] [[c.Software.real_time_framework]]

- repo: https://github.com/colyseus/colyseus
- creator: @endel-dreyer

- [[p.ownedBy]] [[org.lucid-sight]]
- [[p.hasRelatedSolution]] https://github.com/endel/ecs #ecs
- [[p.hasClientSupport]]
   - [[prdct.unity]]
   - [[prdct.defold]]
     - https://docs.colyseus.io/getting-started/defold-client/
   - [[prdct.babylon-js]]
     - https://doc.babylonjs.com/guidedLearning/networking/Colyseus
   - [[prdct.playcanvas]]
     - https://developer.playcanvas.com/en/tutorials/real-time-multiplayer-colyseus/
   - [[prdct.phaser]]
     - https://github.com/colyseus/tutorial-phaser/tree/master
     - https://learn.colyseus.io/phaser
   - [[prdct.construct]]
   - [[prdct.haxe]]
- [[p.hasExample]]
  - [[Tosios|game.tosios]]
  - https://forum.babylonjs.com/t/open-source-multiplayer-3d-rpg-using-colyseus/35733
    - [[p.mentioned]] [[prdct.yuka-ai]]

## Issues

- [Ability to serialize/deserialize Schema on the server side](https://github.com/colyseus/schema/issues/115)
  - "So I guess the option at this point would be to serialize the state to the database continually, but only as a backup. If the server crashes it can reread the state and would send the full update to the clients to ensure they are back in sync. Which is probably what you want anyway."

### Best Practices Limitations

-   Keep your room classes as small as possible, delegating game-specific functionality to other composable structures.
-   Keep your synchronizeable data structures as small as possible
    -   Ideally, each class extending `Schema` should only have field definitions.
    -   Do not implement _heavy_ game logic inside `Schema` structures. _Some_ logic is fine, specially if they're self-contained within the scope of the structure itself, mutating only its own properties.
-   Rooms should have as little code as possible, and forward actions to other structures
-   Your game logic should be handled by other structures, such as:
    -   Custom external functions
    -   The [Command Pattern](https://docs.colyseus.io/best-practices//#the-command-pattern).
    -   An [Entity-Component System](https://docs.colyseus.io/best-practices//#entity-component-system-ecs).


## Resources

### Learning Resources
- https://drive.google.com/file/d/19EyfO5xQUNx4ejxFTz1KYDjzfGo7UPHA/view
  - [full doc available for $10](https://endel.gumroad.com/l/mazmorra)
  - [[p.hasAuthor]] @endel-dreyer
- [Making Online Multiplayer Game Experiences](https://docs.google.com/presentation/d/e/2PACX-1vSjJtmU-SIkng_bFQ5z1000M6nPSoAoQL54j0Y_Cbg7R5tRe9FXLKaBmcKbY_iyEpnMqQGDjx_335QJ/embed?start=false&loop=false&delayms=3000#slide=id.g6de835f45d_0_170)
- [Tetrolyseus](https://blog.s1h.org/colyseus-multiplayer-game/)
- [[Real Time Multiplayer Colyseus Tutorial|ar.real-time-multiplayer-colyseus]]
- https://blog.logrocket.com/building-a-multiplayer-game-with-colyseus-io/
- https://www.smashingmagazine.com/2021/10/real-time-multi-user-game/

## Implementations

- [[game.tosios]]
- [[prdct.t5c]]

## [[prdct.windows.wsl]]

- netsh interface portproxy add not necessary
