---
id: 30icxq3211jpe24dckfzfqu
title: Screeps
desc: 'MMO RTS sandbox game for programmers, wherein the core mechanic is programming your units AI. You control your colony by writing JavaScript which operate 24/7 in the single persistent world filled by other players on par with you.'
updated: 1714060863680
created: 1707316439843
---

- repo: https://github.com/screeps/screeps
- written_in: javascript
- similar: [[prdct.robocode]] [[prdct.robocode.tank-royale]] [[game.screeps]] [[prdct.battlecode]] [[game.space_traders]] ^zwsvp7ab3c0e

## Architecture

- ![](/assets/images/2024-04-04-21-40-04.png)
-   [`launcher`](https://github.com/screeps/launcher) launches the rest of the processes, and it includes the server control GUI.
    
-   [`storage`](https://github.com/screeps/storage) contains a LokiJS-based database, a key-value storage, and a Pub/Sub mechanism. The rest of the processes connect to `storage` to exchange data.
    
-   [`backend`](https://github.com/screeps/backend-local) contains an HTTP server accessed by clients and a CLI server for administration.
    
-   [`engine`](https://github.com/screeps/engine) is the game core. It executes game scripts and interacts with game world objects.
    
-   [`driver`](https://github.com/screeps/driver) is a link between the environment-independent `engine` (that is shared for the official server, standalone server, and in-browser simulation) and the immediate environment that hosts the game engine. You can replace this module with your own one, if you wish to use another method of storing and handling data.
    
-   [`common`](https://github.com/screeps/common) is a shared code base with useful utilities.


- repo: https://github.com/screeps/screeps
- 