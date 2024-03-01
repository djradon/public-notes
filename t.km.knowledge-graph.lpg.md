---
id: JxDLfPHdGwWEUfJFdgOkR
title: Labelled Property Graph
desc: ''
updated: 1709317189848
created: 1638654053180
---

- "LPGs shine brightest in these limited scenarios where edge properties and path discovery are paramount."

- [[c.resource]] https://medium.com/neo4j/graph-modeling-labels-71775ff7d121
  - a label in Neo4j is just a “set membership marker”
  - Use labels to indicate semantic class of information and set membership, and use them to get the speed-ups of “semi-free” indexing
  - Don’t design a data model if you don’t know what queries you want to ask of the database
    - "Data models exist to facilitate answering questions from the databases — they are not for creating pristine semantic models of domains"
    - Creating great semantic models is arguably futile, because a model is a map and the map is not the territory.
