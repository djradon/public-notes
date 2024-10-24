---
id: j6xe4ny38s8isjsx5aogv6y
title: Void Vocabulary of Interlinked Datasets
desc: ''
updated: 1728923435504
created: 1721478684727
---

- https://www.w3.org/TR/void/

## Features

- Links are sometimes published as part of a larger dataset. For example, many of the resources described in the DBpedia dataset are linked via owl:sameAs to other datasets. In other cases, [[linksets|t.cs.web.w3c.rdf.linkset]] are handled as stand-alone sets of triples, independently from either of the two linked datasets. For example, link generation tools such as Silk [SILK] can discover new links between two existing datasets. Both cases—linksets published as part of a larger dataset, and linksets that are independent from the linked datasets—can be described in VoID.

## Definitions

### Datasets

- A dataset is a set of RDF triples that are published, maintained or aggregated by a single provider.
- Unlike RDF graphs, which are purely mathematical constructs [RDF-CONCEPTS], the term dataset has a social dimension: we think of a dataset as a meaningful collection of triples, that deal with a certain topic, originate from a certain source or process, are hosted on a certain server, or are aggregated by a certain custodian. ^2i30z3o7shd9


## References

- [[ar.w3.void]]
- [[sh.question-log.2024.07.20.void-vs-dcat]]
- 