---
id: hse2ejryorhgws5ij8ohjul
title: Clara Rules
desc: 'Retaking rules for (clojure) developers '
updated: 1715182642427
created: 1708585215208
---

- http://www.clara-rules.org/
- [[c.software.rules-engine]]
- written_in: clojure
- related: [[prdct.pathom]]

## Features

- Easily used from Java
  - "In Java, our facts would typically be JavaBeans."
- Simple but expressive
- combine the best ideas from expert systems, functional programming, and the best known develpment practices.

## Approach

- http://www.clara-rules.org/docs/approach/
  - expressiveness: We didn’t want to fall into the trap of most rule engines, which used a limited host language that blocked easy expression or invocation of rich logic. Limited languages are great for limited problems, but they can become an obstacle as problems evolve.
  - Lisp-style macros are what makes Clara possible. At its core, Clara is a collection of macros that takes a set of independent rules, identifies and merges commonality, and compiles those rules into an efficient executable structure.

## Clojure for games

- "There are also experiments with trying to make rule systems like Clara fast enough to use in games."
- "Alex Kehayias gave a talk about designing a functional game engine in ClojureScript, using components, here: https://www.youtube.com/watch?v=TW1ie0pIO_E I thought it was a superb talk. "
- [[prdct.ittyon]]

## References

- [Entity–component–system and Clojure](https://groups.google.com/g/clojure/c/2eBO5ABe7z4?pli=1)