---
id: ew0at1k0xq1kqzjkzagqfhh
title: Linked Data Templates
desc: ''
updated: 1731610426371
created: 1716498518449
---

- https://atomgraph.github.io/Linked-Data-Templates/
- related: [[t.cs.api.hypermedia]] [[t.cs.web.hateoas]] [[prdct.spin]]

## Descriptions

LDT can be used to design ontology-driven Web application programming interfaces (APIs). It provides facilities to define interactions with application resources declaratively using SPARQL commands. It also provides a standard method to evaluate requests into responses over application ontology and dataset.

## Solutions

- [[prdct.atomgraph-processor]]

## Comparisons

### Linked Data Templates vs Linked Data Platform

- Ontology as a declarative representation of the application's operations, dependency on SPARQL, formal valuation of interactions and the support for HATEOAS hypermedia are the main features that distinguish LDT from other Linked Data specifications such as Linked Data Platform [LDP]. Rather than prescribing a single interaction model as does LDP, LDT specifies ontology structure and processing rules that allow applications to define custom interaction models.

### Linked Data Templates vs Hydra

- Hydra Core Vocabulary is a lightweight vocabulary to create hypermedia-driven Web APIs and has similar goals to combine REST with Linked Data principles, but does not employ SPARQL and focuses on JSON-LD

## References

- [[ar.linked-data-templates]]