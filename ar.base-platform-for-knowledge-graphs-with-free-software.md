---
id: pf8h1vgm5j307dsjbmuzz00
title: Base Platform for Knowledge Graphs with Free Software
desc: ''
updated: 1727812972163
created: 1716960385124
---

- https://ceur-ws.org/Vol-3401/paper6.pdf
- mentions: [[prdct.trifid]] [[prdct.lodview]] [[prdct.graph-explorer]] [[prdct.linked-data-viewer]] [[prdct.rdf-surveyor]] [[prdct.shiro]] [[t.cs.data.5-star-open-data-model]] [[prdct.widoco]]
- keywords: [[t.km.knowledge-graph]]

![](/assets/images/2024-10-01-11-42-38.png)

## Abstract

We present an Open Source base platform for the CoyPu knowledge graph project in the resilience domain. We report on our experiences with several tools which are used to create, maintain, serve, view and explore a modular large-scale knowledge graph, as well as the adaptions that were necessary to enable frictionless interaction from both performance and usability perspectives. For this purpose, several adjustments had to be made. We provide a broad view of different programs which are of relevance to this domain. We demonstrate that while it is already possible to achieve good results with free software, there are still several pain points that need to be addressed. Resolution of these issues is often not only a matter of configuration but requires modification of the source code as well.

## Highlights

### Introduction

- While general approaches for KG development and maintenance are proposed, limited guidance regarding the selection of efficient tools for implementing these methodologies is available.

### Related Work

- While certain commercial tools like [[metaphactory|prdct.metaphactory]] or the [[Enterprise Knowledge Graph Platform|prdct.corporate-memory-enterprise-knowledge-graph-platform]] claim to offer comprehensive, all-in-one solutions, free and open-source alternatives often only address specific aspects. Consequently, users seeking to employ free and open-source tools must combine multiple applications and platforms to arrive at a complete knowledge graph platform.

### Solutions and Other Tools

#### Ontology Authoring

- protege for ontology authoring
- [[prdct.widoco]] for documentation and visualization
- [[prdct.rdf-processing-toolkit]] for usage statistics
- [[prdct.rdfunit]]

#### Mapping structured data to RDF data. 

-Several different tools were used by the different project partners, for example [[prdct.tarql]], [[prdct.rdf-processing-toolkit]] or Morph-KGC [ 20 ]. Each tool was chosen by the familiarity of the expert user and applicability to the data source that is to be mapped. Tarql for instance is an excellent choice to map CSV to RDF. RPT on the other hand can easily process CSV, JSON, and XML input files as well as web APIs and remote services using SPARQL, and Morph-KGC can map CSV or connect to SQL databases using [[RML|prdct.rml]].
- Especially the way to register custom functions in RML is quite heavy-handed, whereas RPT allows defining such functions using either JavaScript or Java annotations.