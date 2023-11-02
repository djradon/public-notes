---
id: th97260fqiqad21c69g5rwf
title: A Quadtree Based Synchronization Protocol for Inter Server Game State Synchronization
desc: ''
updated: 1696356514925
created: 1696356076628
---

- #url https://www.sciencedirect.com/science/article/pii/S1389128620313177
- [[c.mention]] [[prdct.named-data-networking]] [[t.cs.game.world.quad-tree-synchronization-protocol]]
- #repo https://github.com/phylib/QSPArtifacts


## Highlights

- "the quadtree is built as a Merkle tree, meaning that every non-leaf node of the tree is assigned a cryptographic hash value, which is calculated by hashing the child nodes of the corresponding node. Thereby, a single changed object somewhere in the overall region is recognized by a change of the tree’s root hash. Starting from the root, it is possible to track the change down to the single leaf node that changed."