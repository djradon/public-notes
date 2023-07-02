---
id: cqtllme7cw60cs9vh18yb2s
title: Hypergraph
desc: ''
updated: 1688223102523
created: 1652767633550
---

#aka [[prdct.hode.rslt]]
- likely many definitions, but I like TypeDB's:
  - [[p.hasSource]] [[Modelling Data with Hypergraphs|ar.medium.modelling-data-with-hypergraphs]]
    - a hypergraph consists of a non-empty set of vertices and a set of hyperedges;
    - a hyperedge is a finite set of vertices (distinguishable by specific roles they play in that hyperedge);
    - a hyperedge is also a vertex itself and can be connected by other hyperedges.


![](/assets/images/2022-12-10-13-25-23.png)

- [[p.hasRelatedTopic]]
  - [[t.cs.graph.hyperedge]]

## [[c.Thought]]

- ![[daily.journal.2023.06.28#^vnkm9vka0yb7]]

## [[c.Resource]]

- [[ar.thinkmind.the-typed-graph-model]]
- [[Modelling Data with Hypergraphs. A closer look at the TypeDB hypergraph|ar.medium.modelling-data-with-hypergraphs]]
- https://news.ycombinator.com/item?id=32283022
- https://people.csail.mit.edu/jshun/6827-s22/lectures/lecture10-2.pdf
- [[ar.opencog.graphs-metagraphs-ram-cpu]]
  - "The naive representation for the hypergraph is a straight-forward extension of the edge table...
![](/assets/images/2023-05-19-16-20-39.png)
  - "The vertex list may be empty, may hold one, or more vertexes. It is necessarily ordered (and thus not a set) and may contain repeated entries (a vertex may appear more than once in the list)"
- [Two monads for graphs](https://arxiv.org/pdf/1804.09408.pdf) has some interested visualizations
  - ![](/assets/images/2023-07-01-06-45-50.png)
- https://gitlab.com/graphviz/graphviz/-/issues/1911 talks about visualization, has this cool thing: ![](/assets/images/2023-07-01-07-06-16.png)