---
id: zgsjt50m8iw9594pv9pps63
title: RDF-Ext
desc: 'JavaScript library that extends the RDF/JS specs to handle RDF data in a developer-friendly way'
updated: 1729873340507
created: 1729872629393
---

- https://rdf-ext.org/
- related: [[prdct.grapoi]] 

## Scope

The scope of this project is to provide a flexible standard developer kit based on the RDF/JS specification for working with RDF data in various environments. The primary focus is on supporting Node.js and browsers, but it's also designed to work with other JavaScript runtimes. Features are implemented in a modular fashion. Individual libraries can be used without the core RDF-Ext library together with other standard RDF/JS libraries. The following use cases are covered:

-   Parse and serialize RDF standard formats such as Turtle, N-Triples, and JSON-LD.
-   Read and write RDF data:
    -   File system: Load and save RDF data from files and handle file and folder structures representing Named Graphs.
    -   SPARQL: Handle requests and parse results.
    -   SPARQL Graph Store: Handle requests, parse, and serialize RDF data.
    -   HTTP: Send and receive RDF data over plain HTTP and handle parsing and serialization.
-   Validation:
    -   SHACL: An extendable SHACL engine is provided.
-   Fluent interface traversing: Traverse and manipulate RDF data using a fluent interface.
-   Object RDF Mapper (ORM): Read and manipulate RDF data using object-oriented programming techniques.
-   Frontend: Generic components for showing and editing RDF data.
    -   Tables for triples and resources: The toolset includes components for displaying RDF data in tables, making it easy to visualize and work with RDF data in a tabular format.
    -   Network diagram: The toolset includes a component for displaying RDF data as a network diagram, making it easy to visualize the relationships between different resources in the data.

Overall, RDF-Ext aims to provide all features one would expect from an RDF SDK for JavaScript.