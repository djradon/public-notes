---
id: zni79itus3zhhfw716fe2ur
title: Delta an Ontology for the Distribution of Differences between Rdf Graphs
desc: ''
updated: 1720359704255
created: 1720359458817
---

- https://www.w3.org/DesignIssues/Diff

## Highlighs

- concurrent changes may be completely irreconcilable
  - (so live with it)
- Problems with the line-oriented approach:
  - However, when files are edited by hand, small changes to the data naturally result in small textual diffs. But since the difference is expressed as the difference between two text files, not the difference between two graphs, the delta is dependent on the graph serialization. It's not enough to have the original graph to use the delta; one needs a copy of the particular serialization.
  - Pretty-printing algorithms reduce the large number of possible serializations of an RDF graph to a few actual serializations.
  - The difference engine[Kly04] produces human-readable difference descriptions using an algorithm analogous to comparing pretty-printed graphs; its descriptions are not sufficient to reconstruct one graph from the other, however.
  - The straightforward pretty-printing algorithm works in the obvious way when all the nodes are named (either with URIs or literals): triples are sorted by subject, and those that share a subject are grouped together. 
  - Notation3 has syntax for grouping triples that shared predicates.