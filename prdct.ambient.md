---
id: mmtnuc9z89pdxapnk898cfm
title: Ambient
desc: >-
  runtime for building high-performance multiplayer games and 3D applications,
  powered by WebAssembly, Rust and WebGPU
updated: 1698252759199
created: 1696363752606
---


- [[c.software.game-engine]] [[c.software.entity-component-system]]
- repo: https://github.com/AmbientRun/Ambient
- written-in: #rust

## Features

- **Ambient Proxy**: An important part of building multiplayer projects is being able to share them with other people. Traditionally, this involves port forwarding, NAT punchthrough, running a dedicated server, and other complicated networking trickery. Ambient provides a solution to this problem: the Ambient Proxy.
- Entities contain components, which are typed pieces of data, and these are acted upon with systems ^1nl6ma5m12zt


## Cons

- Networked components are automatically synchronized to all clients, ensuring a consistent experience across all players; instead of grappling with complex networking intricacies, developers can focus on building their server and client-side logic. ^zumxj8d7vwkb

![[ECS|t.cs.entity-component-system#^h56imtf2ip3n]]