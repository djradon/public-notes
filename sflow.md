---
id: ggw3ek46ptgebsgxgihr1dh
title: Semantic Flow
desc: ontology, tooling, and workflow for publishing semantic data
updated: 1731039033868
created: 1716959415785
---

- requirements: [[sflow.requirements]]
- issues: [[sflow.issues]]

## Features

- entity-level granularity
- use github or gitlab to manage namespaces using [[sflow.concepts.sf-root-repo]] and mint IRIs
- an [[sflow.concepts.sf-data-repo]] could have files/distributions for more than one namespace, so it should have each of those namespaces segregated by a top-level folder
- scan IRI sources,  
- maybe generate [[sflow.concepts.reference-pages]] dynamicall like [[prdct.docsify]]



## Relationship with Kosmion

- [[ko]] is a unorthodox, relator-based foundational ontology developed side-by-side with Semantic Flow. 
- hopefully Semantic Flow has no dependencies on Kosmion and can be used for any kind of RDF data


## References

- [[ar.base-platform-for-knowledge-graphs-with-free-software]]
- https://www.rockyourcode.com/how-to-deploy-eleventy-to-github-pages-with-github-actions/