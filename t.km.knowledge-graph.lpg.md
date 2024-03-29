---
id: JxDLfPHdGwWEUfJFdgOkR
title: Labelled Property Graph
desc: ''
updated: 1711696792763
created: 1638654053180
---

- "LPGs shine brightest in these limited scenarios where edge properties and path discovery are paramount."

## Properties of Properties:

In the world of LPGs, edges can bear their own properties, allowing for the inclusion of valuable metadata such as the source of information, date of assertion, and confidence level. This can be emulated with objects in standard RDF but unfortunately there is a performance cost. A better approach is RDF-* and SPARQL-*, which is about to be standardized, and is already supported by several RDF databases.

## Property Path Discovery:

LGPs have an advantageous ability to traverse the shortest path between two nodes, which is valuable for unraveling complex relationships and uncovering hidden insights. While this may not be a pivotal concern for all domains, it holds particular significance for those where relationships are multi-faceted and require in-depth exploration. This is only important for certain domains, such as social networks, so it is of limited importance. However, there is nothing about property graphs that is special here, as it’s just a function of the query language. Unfortunately, SPARQL doesn’t include this, but any RDF database (including Fluree) can implement this operation, if the application demands for it.

It’s important to note that LPGs shine brightest in these limited scenarios where edge properties and path discovery are paramount. The beauty of the RDF ecosystem lies in its versatility and adaptability. The introduction of RDF-* and SPARQL-* speaks to the growing recognition of these specialized features within the RDF paradigm.

- [[c.resource]] https://medium.com/neo4j/graph-modeling-labels-71775ff7d121
  - a label in Neo4j is just a “set membership marker”
  - Use labels to indicate semantic class of information and set membership, and use them to get the speed-ups of “semi-free” indexing
  - Don’t design a data model if you don’t know what queries you want to ask of the database
    - "Data models exist to facilitate answering questions from the databases — they are not for creating pristine semantic models of domains"
    - Creating great semantic models is arguably futile, because a model is a map and the map is not the territory.

## References

- https://flur.ee/fluree-blog/rdf-versus-lpg/