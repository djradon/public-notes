---
id: 4gxa6yhm9njx4ptunjqnht7
title: dotNetRDF
desc: 'A complete library for parsing, managing, querying and writing RDF; A common .NET API for working with RDF triple stores such as AllegroGraph, Jena, Stardog and Virtuoso'
updated: 1710862561448
created: 1709139426746
---

- supports: [[prdct.RDF-star]] [[prdct.sparql.star]]
- supports: [[prdct.allegrograph]] [[prdct.virtuoso]] [[prdct.jena]] [[prdct.stardog]]
- author: @ruben-taelman

## Description

- A complete library for parsing, managing, querying and writing RDF.
- A common .NET API for working with RDF triple stores such as AllegroGraph, Jena, Stardog and Virtuoso.
- A suite of command-line and GUI tools for working with RDF under Windows

## Questions

- any advantage to one backend over the other?
  - https://github.com/dotnetrdf/dotnetrdf/discussions/491 makes it sound like native virtuoso is out, but no big loss
  - probably best to use the sparql interface anyhow unless you have a reason not to. 