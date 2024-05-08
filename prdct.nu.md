---
id: phth120azrbsgz9ipa3pik1
title: Nu
desc: 'first practical functional 2D and 3D cross-platform game engine. Built in F#, it offers a declarative MVU-based API called MMCC (Model-Message-Command-Content'
updated: 1715184051802
created: 1708537637631
---

- [[c.software.game-framework]]
- repo: https://github.com/bryanedds/Nu
- related: [[ar.youtube.platform-as-a-reflection-of-values]]

## Features

- first practical functional 2D and 3D cross-platform game engine. Built in F#, it offers a declarative MVU-based API called MMCC (Model-Message-Command-Content
- Real-time WYSIWYG editing with hot asset and live code reloading, and the ability to undo and redo gameplay.
- Recursive Prefab-like functionality via Entity Structure Propagation.

### MVCC

Model-View-Update (or MVU) is the 'killer app' of functional programming. Until MVU came along, most arguments about the benefits of functional programming resided primarily in the space of the theoretical. But when Elm introduced the world to MVU with its incredibly clean authoring form factor, the space of discussion changed forever.

With Nu's generalization of MVU via MMCC (Model-Message-Command-Content), it is the first and still only practical game engine positioned to bring the killer benefits of this declarative development form factor to game developers.

### Immutability

- By default in the editor, Nu is configured to run in an immutable mode. In this mode, all of the simulation backing data encapsulated behind the World API is implemented with functional data structures that can be snapshotted and restored. This snapshotting is how Nu's editor, Gaia, implements its Undo and Redo operations. However, for optimal performance, Nu is configured to use mutating data structures under the hood instead when outside of the editor. Nu can be configured to run either way in both contexts, however.

## Examples

- [[game.omniblade]]