---
id: ggw3ek46ptgebsgxgihr1dh
title: Semantic Flow
desc: ontology, tooling, and workflow for publishing semantic data
updated: 1750445158820
created: 1716959415785
---

- requirements: [[sflow.requirements]]
- issues: [[sflow.issues]]

A **dereferenceable semantic web** (.9) - every IRI becomes an entry point into your knowledge graph. That's ambitious but creates incredible discoverability. The reverse index aspect is brilliant for exploration.

## Features

- RDF dataset-series oriented for semantic versioning and provenance
  - every named entity can have a catalog series, which describes facilitates discovery by describing entity-related resources (including the default dataset series)
- use github or gitlab to manage namespaces using [[sflow.concepts.sf-root-repo]] and mint IRIs
- an [[sflow.concepts.sf-data-repo]] could have files/distributions for more than one namespace, so it should have each of those namespaces segregated by a top-level folder
- scan IRI sources,  
- maybe generate [[sflow.concepts.reference-pages]] dynamicall like [[prdct.docsify]]


## Related Prodcuts / Possible Components

- [[prdct.comunica.query-sparql-file]]

