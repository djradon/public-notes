---
id: 8nvkbc4oex3mqj7x39u3qtv
title: >-
  'Jekyll RDF: Template Based Linked Data Publication with Minimized Effort and
  Maximum Scalability'
desc: ''
updated: 1727978631957
created: 1727123814907
---

- https://svn.aksw.org/papers/2019/ICWE_JekyllRDF/public.pdf
- topics: [[t.cs.data.visualization]] [[t.cs.data.publication]] [[t.cs.web.static-site-generator]] [[t.cs.data.linked]]


## Abstract

Over the last decades the Web has evolved from a human– human communication network to a network of complex human–machine interactions. An increasing amount of data is available as Linked Data which allows machines to “understand” the data, but RDF is not meant to be understood by humans. With Jekyll RDF we present a method to close the gap between structured data and human accessible exploration interfaces by publishing RDF datasets as customizable static HTML sites. It consists of an RDF resource mapping system to serve the resources under their respective IRI, a template mapping based on schema classes, and a markup language to define templates to render customized resource pages. Using the template system, it is possible to create domain specific browsing interfaces for RDF data next to the Linked Data resources. This enables content management and knowledge management systems to serve datasets in a highly customizable, low effort, and scalable way to be consumed by machines as well as humans.

## Highlights

### Existing Visualization Applications

A great variety of applications exist to visualize RDF data. Such applications are table based triple explorers, like [[prdct.pubby]], [[prdct.lodview]], and [[prdct.ld-viewer]]/DBpedia Viewer and visual graph explorers like [[prdct.lodlive]], [[prdct.lodmilla]], and [[prdct.linked-data-maps]]

Templating systems usually provide a flexible approach for inserting data into a scaffolding of an HTML page. The [[SPARQL Web Pages|prdct.sparql-web-pages-uispin]] system defines a templating language that allows to incorporate data from an RDF graph into HTML and SVG documents. It is shipped with the commercial version of the TopBraid Composer. A similar approach is followed by LESS [5] which later was integrated with the [[OntoWiki|prdct.ontowiki]]. The OntoWiki Site Extension allows to render RDF resources in HTML views using a PHP base templating language. To serve the required representation of a Linked Data resources the OntoWiki Linked Data server uses content negotiation to dynamically serve an HTML view to web browsers and an RDF representation to Linked Data systems

A different approach to provide customizable web interfaces to explore and even edit RDF data is presented by Khalili et al. with the [[LD-R|prdct.ld-r]]. It provides a framework to define Linked Data-driven Web Components in JavaScript. With this framework it is possible to reuse existing components and compose new dynamic web interfaces. A similar approach to build Semantic Interfaces for Web Applications is presented with the [[MIRA framework|prdct.mira]] [7]. It defines an abstract interface definition that composes elements to form a hierarchy of widgets. These widgets can be used in JavaScript applications to build responsive user interfaces