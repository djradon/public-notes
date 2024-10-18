---
id: q4jqx5qr6hbp6fo3pfvh042
title: Immutability
desc: ''
updated: 1729278810678
created: 1723213911939
---

## Issues

- RDF isn't naturally immutable because a graph is a naturally a dynamic thing
- if you want some degree of immutability, there's going to have to be a meta-lattice that points to "what's current" (as in valid)
  - or you could imagine relators that are all attached to an alias, and queries have to pick out the currently active one.
- perhaps small collections of triples, aka [[ko.concepts.micro-graphs]] become the fundamental unit of data. 
- to keep track of history, i.e., successor and predecssor micro-graphs, use the [[ko.concepts.meta-lattice]] 


## Prior Art

- [[prdct.Fluree]] is append-only, 