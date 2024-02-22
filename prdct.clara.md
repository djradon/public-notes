---
id: hse2ejryorhgws5ij8ohjul
title: Clara
desc: ''
updated: 1708585873148
created: 1708585215208
---

- [[c.software.rules-engine]]
- written_in: clojure

## Approach

- http://www.clara-rules.org/docs/approach/
  - expressiveness: We didn’t want to fall into the trap of most rule engines, which used a limited host language that blocked easy expression or invocation of rich logic. Limited languages are great for limited problems, but they can become an obstacle as problems evolve.
  - Lisp-style macros are what makes Clara possible. At its core, Clara is a collection of macros that takes a set of independent rules, identifies and merges commonality, and compiles those rules into an efficient executable structure.