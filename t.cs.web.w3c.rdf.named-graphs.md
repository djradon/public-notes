---
id: 836unuyt1okg2szo6u8hn1g
title: Named Graphs
desc: ''
updated: 1726339489924
created: 1724995299262
---

- In Carroll et al. [CARROLL-05], a named graph is defined as a pair comprising an IRI and an RDF graph. The notion of RDF interpretation is extended to named graphs by saying that the graph IRI in the pair must denote the pair itself. This non-ambiguously answers the question of what the graph IRI denotes. This can then be used to define proper dataset semantics, as shown in Section 3.3. Note that it is deliberate that the graph IRI is forced to denote the pair rather than the RDF graph. This is done in order to differentiate two occurrences of the same RDF graph that could have been published at different times, or authored by different people. A simple reference to the RDF graph would simply identify a mathematical set, which is the same wherever it occurs.

## Semantics

Many options, none chosen:

3.1 Named graphs have no meaning
3.2 Default graph as union or as merge
3.3 The graph name denotes the named graph or the graph
3.4 Each named graph defines its own context
3.5 Named graph are in a particular relationship with what the graph name dereferences to
3.6 Quad semantics
  - extends RDF semantics instead of re-using

"the Working Group discussed the possibility to define several semantics, among which an implementation could choose, and provide the means to declare which semantics is adopted.

This was not retained eventually, because of the lack of experience, so there is no definite option for this"

## References

- https://www.w3.org/TR/rdf11-datasets/