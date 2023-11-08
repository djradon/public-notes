---
id: hs3pfpuq926ytwh3xqvsdgc
title: Nakama
desc: >-
  the first open-source distributed server for social and realtime games and
  apps
updated: 1698252759288
created: 1656792485964
---

- [[c.software.game-platform]] [[c.software.game-framework]]
- #repo https://github.com/heroiclabs/nakama
- [[p.writtenIn]] #go
- [[p.hasScriptingLanguage]] #typescript [[prdct.lua]]
- [[p.hasClientSupport]] [[prdct.unity]] [[prdct.unreal]] [[prdct.godot]] [[prdct.defold]] [[prdct.cocos2d]] #javascript #java #c #c++ [[prdct.flutter]]
- [[p.hadPricing]] https://heroiclabs.com/pricing/
- [[p.hadEtymology]]  In Japanese, the word nakama 仲間 means "someone who's in the same group as you," or can refer to the group itself.
- [[p.writtenIn]] 
  - Go 86.5%
  - Lua 5.1%
  - TypeScript 4.4%
- [[p.wasBuiltBy]] [[org.heroic-labs]]

## Features
-   Low-level control of real-time [routing and delivery](https://heroiclabs.com/docs/nakama/server-framework/streams/)
-   Intercept and override functionality with [hooks](https://heroiclabs.com/docs/nakama/server-framework/introduction/#hooks)
-   Define and call [RPC functions](https://heroiclabs.com/docs/nakama/server-framework/introduction/#rpc-functions)
-   Run background server cron [jobs](https://heroiclabs.com/docs/nakama/guides/server-framework/background-jobs/)
-   [Access controls](https://heroiclabs.com/docs/nakama/concepts/storage/permissions/) and [API guarding](https://heroiclabs.com/docs/nakama/guides/server-framework/guarding-apis/)
-   Low-level control of real-time [routing and delivery](https://heroiclabs.com/docs/nakama/server-framework/streams/)


## [[c.limitation]]

- The JavaScript runtime code is fully sandboxed and cannot access the filesystem, input/output devices, or spawn OS threads or processes.

- The JavaScript runtime is powered by the goja VM which currently supports the JavaScript ES5 spec. The JavaScript runtime has access to the standard library functions included in the ES5 spec.

- There is no support for libraries that require Node, web/browser APIs, or native support (e.g. via Node).

- You cannot call TypeScript functions from the Go runtime, or Go functions from the TypeScript runtime.

The JavaScript runtime code is executed in instanced contexts (VM pool). You cannot use global variables as a way to store state in memory or communicate with other JS processes or function calls.
  
## [[p.provokedThoughts]]

- [Storage Engine] seems key-value/JSON-based (https://heroiclabs.com/docs/nakama/concepts/storage/collections/)

## [[p.hasFeature]]

-   **Users** - Register/login new users via social networks, email, or device ID.
-   **Storage** - Store user records, settings, and other objects in collections.
-   **Social** - Users can connect with friends, and join groups. Builtin social graph to see how users can be connected.
-   **Chat** - 1-on-1, group, and global chat between users. Persist messages for chat history.
-   **Multiplayer** - Realtime, or turn-based active and passive multiplayer.
-   **Leaderboards** - Dynamic, seasonal, get top members, or members around a user. Have as many as you need.
-   **Tournaments** - Invite players to compete together over prizes. Link many together to create leagues.
-   **Parties** - Add team play to a game. Users can form a party and communicate with party members.
-   **Runtime code** - Extend the server with custom logic written in Lua, TypeScript/JavaScript, or native Go code.
    - [[**NOTE**|p.hadLimitation]]
      - There is no support for libraries that require Node, web/browser APIs, or native support (e.g. via Node).
      - The use of multi-threaded processing is not supported in the JavaScript runtime.
-   **Matchmaker**, **dashboard**, **metrics**, and [more](https://heroiclabs.com/docs).  

## [[t.cs.sd.architecture]]

- https://heroiclabs.com/docs/nakama/getting-started/architecture/
  - "If data needs to be distributed to clients live, streams are the way it gets there. Individual player sessions join and leave streams, like subscribing and unsubscribing to a continuous flow of messages."

- [[c.software.game-platform]] [[c.software.game-framework]]