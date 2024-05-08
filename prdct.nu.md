---
id: phth120azrbsgz9ipa3pik1
title: Nu
desc: 'first practical functional 2D and 3D cross-platform game engine. Built in F#, it offers a declarative MVU-based API called MMCC (Model-Message-Command-Content'
updated: 1715183762495
created: 1708537637631
---

- [[c.software.game-framework]]
- repo: https://github.com/bryanedds/Nu

## Features

- first practical functional 2D and 3D cross-platform game engine. Built in F#, it offers a declarative MVU-based API called MMCC (Model-Message-Command-Content
- Real-time WYSIWYG editing with hot asset and live code reloading, and the ability to undo and redo gameplay.
- Recursive Prefab-like functionality via Entity Structure Propagation.

### Immutability

- By default in the editor, Nu is configured to run in an immutable mode. In this mode, all of the simulation backing data encapsulated behind the World API is implemented with functional data structures that can be snapshotted and restored. This snapshotting is how Nu's editor, Gaia, implements its Undo and Redo operations. However, for optimal performance, Nu is configured to use mutating data structures under the hood instead when outside of the editor. Nu can be configured to run either way in both contexts, however.

## Examples

- [[game.omniblade]]