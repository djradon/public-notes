---
id: ln9msn4gjrhb2y18855kgi9
title: LDflex a Read Write Linked Data Abstraction for Front End Web Developers
desc: ''
updated: 1714683841991
created: 1714683078480
---

- https://drive.verborgh.org/publications/iswc2020-ldflex.pdf
- mentions: [[prdct.comunica]] [[prdct.rdf-js]]

## Abstract

Many Web developers nowadays are trained to build applications with a user-facing browser front-end that obtains predictable data structures from a single, well-known back-end. Linked Data invalidates such assumptions, since data can combine several ontologies and span multiple servers with different apis. Front-end developers, who specialize in creating end-user experiences rather than back-ends, thus need an abstraction layer to the Web of Data that integrates with existing frameworks. We have developed LDflex , a domain-specific language that exposes common Linked Data access patterns as reusable JavaScript expressions. In this article, we describe the design and embedding of the language, and discuss its daily usage within two companies. LDflex eliminates a dedicated data layer for common and straightforward data access patterns, without striving to be a replacement for more complex cases. The use cases indicate that designing a Linked Data developer experience—analogous to a user experience—is crucial for adoption by the target group, who in turn create Linked Data apps for end users. Crucially, simple abstractions require research to hide the underlying complexity.


## Highlights

- The difficulty [of making Linked Data accessible to front-end developers] lies in finding an abstraction that hides irrelevant rdf complexities, while still exposing the unbounded flexibility that Linked Data has to offer. Abstractions with rigid objects do not suffice, as their encapsulation tends to conceal precisely those advantages of rdf.