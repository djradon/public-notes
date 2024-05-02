---
id: kyn0sqveeg53pjp8h632aes
title: Rdf4j
desc: ''
updated: 1714678887784
created: 1699472038413
---

- similar: [[prdct.jena]]

## Comparison

### rdf4j vs jena

- ~~"offers SparqlBuilder which is safe, builder-pattern way of constructing a query, which has no (mature) alternative in native Apache Jena-land.~~ Jena's [QueryBuilder](https://jena.apache.org/documentation/extras/querybuilder/)
- RDF4J has no direct equivalent to Jena's Ontology API (which contains the OntClass class). Instead, in RDF4J you always work with RDF only. Models are pure RDF graphs.

## Integrations

### Spring Data

- [[prdct.rdf4j-spring]]


## References

- https://www.donaldmcintosh.net/blog/fuseki-commentary
- https://www.youtube.com/watch?v=u_Hf50-3wZY
- https://rdf4j.org/documentation/programming/spring/