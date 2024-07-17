---
id: ajtyyiy5j7attle4zo8h8im
title: Datasets
desc: 'a collection of RDF graphs'
updated: 1721251715004
created: 1721250549704
---

- "it is sometimes desirable to work with multiple RDF graphs while keeping their contents separate. RDF datasets support this requirement."

- "We informally use the term RDF source to refer to a persistent yet mutable source or container of RDF graphs. An RDF source is a resource that may be said to have a state that can change over time. A snapshot of the state can be expressed as an RDF graph. For example, any web document that has an RDF-bearing representation may be considered an RDF source. Like all resources, RDF sources may be named with IRIs and therefore described in other RDF graphs."

- "An RDF dataset is a collection of RDF graphs. All but one of these graphs have an associated IRI or blank node. They are called named graphs, and the IRI or blank node is called the graph name. The remaining graph does not have an associated IRI, and is called the default graph of the RDF dataset."

- "There are many possible uses for RDF datasets. One such use is to hold snapshots of multiple RDF sources."

- "An RDF document is a document that encodes an RDF graph or RDF dataset in a concrete RDF syntax, such as Turtle"

## References

- https://www.ateam-oracle.com/post/rdf-datasets-named-and-default-graphs-concepts-and-how-to-query-them
- https://www.w3.org/TR/rdf11-concepts/