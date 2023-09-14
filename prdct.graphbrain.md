---
id: nrTb5pttcGNuF7maN7sTS
title: Graphbrain
desc: >-
  an Artificial Intelligence open-source software library and scientific
  research tool
updated: 1694644716454
created: 1644488300455
---

- #url https://graphbrain.net/
- [[p.writtenIn]] [[t.cs.languages.Python]]
- #aka "An OpenCog that works"

## [[c.Feature]]

- provides an actual database system that allows for persistent storage and manipulation of semantic hypergraphs.

## [[c.Con]]

- single backend implementation, that is based on LevelDB (a very efficient sorted key-value store that is stored in a local directory). Hypergraphs stored in this format can only be accessed by one process/thread at a time.

## [[c.Highlight]]

- Graphbrain is built around a unifying concept: the [[Semantic Hypergraph (SH)|t.cs.graph.semantic-hypergraph]], which makes it possible to represent a natural language sentence such as “Einstein first published the theory of relativity in 1905” as an ordered, recursive hyperlink
  - http://graphbrain.net/manual/notation.html 
