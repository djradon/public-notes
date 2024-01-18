---
id: spp0at53ryx9tkr21knzy9p
title: Spatio-Temporal RDFb
desc: ''
updated: 1705548425649
created: 1705548129652
---

The current standard query language for RDF, i.e., SPARQL 1.1, does not support spatio–temporal query patterns on sensor data. Recently, there have been several complimentary works towards supporting spatio–temporal queries on RDF. For example, to enable spatio–temporal analysis, in [19], Perry et al. propose the SPARQL-ST query language and introduce the formal syntax and semantics of their proposed language. SPARQL-ST is extended from the SPARQL language to support complex spatial and temporal queries on temporal RDF graphs containing spatial objects. With the same goal as SPARQL-ST, Koubarakis et al. propose st-SPARQL [20]. They introduce stRDF as a data model to model spatial and temporal information and the stSPARQL language to query against stRDF. Another example is [21], where Gutierrez et al. propose a framework that introduces temporal RDF graphs to support temporal reasoning on RDF data. In this approach, the temporal dimension is added to the RDF model. The temporal query language for temporal RDF graphs is also provided. However, the aforementioned works commonly focus on enabling spatio–temporal query features, but hardly any of them fully address the performance and scalability issues of querying billions of triples [22].

## Solutions

- [[prdct.eagle]]

## Resources

- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6832792/