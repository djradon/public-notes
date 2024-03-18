---
id: 792yk3qq3uv43esze394zlh
title: Databus
desc: 'platform for agile data integration, collaboration, and automation via a structured metadata Knowledge Graph'
updated: 1710791662112
created: 1710791662112
---

- [[c.software.data-management-platform]]
- docs: https://dbpedia.gitbook.io/databus

## Description

- The Databus implements well-known concepts from Software Engineering such as agile rapid prototyping, build automation, test-driven development for Data Engineering and connects data via a loosely-coupled bus system and a common, but extensible metadata format through state-of-the-art semantic technologies such as ontologies, SPARQL, SHACL and Linked Data.

## Features

- Semantic Layer On-Top: Databus is a proud member of the Open Energy Family and deployed as an additional semantic layer over the various existing databases to extend the underlying rigid metadata schemas and enable search, persistent IDs and provenance tracking of scientific results.

## Use cases

## data version control

- Databus uses the Apache Maven concept hierarchy (group, artifact, version) and ports it to a Linked Data based platform, in order to manage data pipelines and enable automated publishing and consumption of data.
  - we define **compiling of data** as the process that converts, transforms or translates data geared to the needs of a specific target application

## Automated deployment

- Dataset Publication: microservice's configuration and data can be published as individual or combined datasets on the DBpedia Databus. For example, all the configurations can be published as a single dataset where different content variants serve for searching the right configuration. Datasets can be versioned, allowing for easy rollbacks and traceability.
- Semantic Queries: DBpedia Databus supports semantic querying, allowing microservices or deployment engine to query for specific data subsets or retrieve relevant configurations based on their requirements.

## Concepts

- Collection: a labelled SPARQL query that is retrievable via URI


## References

- https://dbpedia.gitbook.io/databus
- https://dbpedia.gitbook.io/databus/v/download-client