---
id: apimihsw5cjqs9mb538lqxv
title: ONT-API
desc: 'OWL-API over Apache Jena is a RDF-centric Java library to work with OWL2'
updated: 1714576199338
created: 1714575962243
---

- repo: https://github.com/owlcs/ont-api
- docs: https://github.com/owlcs/ont-api/wiki
- related: [[prdct.jena]]

## Pros

- allows to use an API that meets the modern OWL specification along with other Jena-compatible products. This can be also useful to the OWL-API users, because the RDF based solution is more flexible and universal, which allows solving a number of OWL-API typical problems. 
  - Instead of mapping RDF to OWL and back that is offered by OWL-API default implementation, in ONT-API there is reading OWL from RDF and writing OWL to RDF, which, actually, is the only true-way, just because OWL is nothing but a subset of RDF. In the ONT-API reading and writing an ontology from a file or a stream happen through Jena RIOT, however, the original OWL-API mechanisms to read/write also remain working, and even are used explicitly if the data format is not supported by Jena (e.g. Functional Syntax, Manchester Syntax, OWL/RDF, etc)
  - ONT-API supports all OWL-API features and options, but they are somewhat expanded. Instead of the original OWL-API interfaces, in ONT-API there are the overridden ones with several additional methods to access to Jena-API. ONT-API IS OWL-API, and can be used in all places where OWL-API is used. And if you don't accept this, then you're, probably, don't need ONT-API at all. It is always possible to use the original OWL-API or its parts in conjunction with ONT-API, for example, you can just copy an ontology from the ONT-API manager to the OWL-API-impl manager and vice versa.

## Cons

A possible downside of this approach might be different performance and memory consumption (in comparison with default OWL-API implementation), but recent research shows that such concerns may not always be justified.