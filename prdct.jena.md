---
id: 1x3lenylbdctmrkbdkn2v0x
title: Jena
desc: 'semantic-web framework for Java which includes a number of different semantic-reasoning modules and rdf-star support'
updated: 1714576388877
created: 1698707121812
type: "[[c.software.database.graph.rdf]]"
---

- url https://jena.apache.org
- similar-to: [[prdct.rdf4j]]
  - "Jena is similar to RDF4J (formerly OpenRDF Sesame); though, unlike RDF4J, Jena provides support for OWL (Web Ontology Language). "
- related: [[prdct.jena-geo]] 

## Features

- [GeoSPARQL](https://jena.apache.org/documentation/geosparql/) ^lfnls4qmhyho

## Issues

- chatgpt.4: "while Jena can handle multiple inheritance in the RDF/OWL sense, translating this directly into Java classes can be challenging. You might need to design your Java class model differently, potentially using interfaces, composition, or other design patterns to represent the multiple inheritance found in the ontology."
- only OWL-1 support, but [[prdct.ont-api]] has OWL2

## Comparison

![[prdct.rdf4j#rdf4j-vs-jena]]

## Resources

- https://medium.com/duda/simplifying-your-structured-data-model-using-apache-jena-545dd93236a8

### Learning Resources

- https://jena.apache.org/getting_started/
- [[book.design-and-implementation-of-ontologies-in-java-and-apache-jena]]

## References

- https://stackoverflow.com/questions/76512856/getting-all-the-owl-classes-in-an-owl-rdf-schema-using-rdf4j