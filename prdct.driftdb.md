---
id: w4s74qsctnz6669tvulo6a7
title: DriftDB
desc: 'real-time data backend that runs on the edge'
updated: 1712900296400
created: 1705596212809
---

- [[c.Software.real_time_framework]]
- no commits since Aug. '23
- url: https://driftdb.com/
- written_in: rust
- repo:  https://github.com/drifting-in-space/driftdb

## Description

Clients connect to it directly over a WebSocket. It supports a number of messaging primitives, including:

-   Publisher / subscriber channels (PubSub)
-   Key/value storage with subscriptions
-   Ordered streams

## Use cases

As a general rule, DriftDB is useful any time you wish you could connect directly from one browser to another, or from a non-web-connected backend (e.g. background task) to a browser. Examples include:

- Backend for state synchronization in real-time collaborative apps (e.g. a whiteboard or casual multiplayer game)
- Streaming build logs in real time in a CI/CD system
- WebRTC signaling

## Demos

- [Voxel Editor](https://demos.driftdb.com/voxel?_driftdb_room=NsCCT2QyUhIRAL6w9yeTDeae) #cool

## References

- https://news.ycombinator.com/item?id=34639728