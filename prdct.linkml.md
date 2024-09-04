---
id: uhagejfd79c8isushtaciux
title: LinkML
desc: 'general purpose modeling language that can be used with linked data, JSON, and other formalisms'
updated: 1725421403519
created: 1696739554441
---

- url: https://linkml.io
- repo:  https://github.com/linkml/linkml
- written-in: #python
- similar: [[prdct.aml]]
- [[p.alternativeTo]] [[prdct.json-schema]]
- [[p.supports]] 
  - [[t.cs.sd.mixin]] 
  - [[prdct.rdf]] see https://linkml.io/linkml/intro/tutorial04.html
- [[c.feature.possible]] 
  - [[prdct.typedb]] converter
- related: https://github.com/linkml/linkml-owl

## Features

- LinkML is designed to work in harmony with other frameworks, including both semantic RDF-based frameworks, as well as frameworks that are more familiar to developers such as JSON.

### JSON-LD support

- [[prdct.JSON-LD]] contexts and JSON-Schema provide distinct ways of describing your data, with JSON-Schema providing the structural description of how your information is organized, and contexts providing the semantics (or at least a loose semantics consisting of reuse of URIs). Despite these distinct purposes there is a lot of overlap and many organizations end up manually maintaining these and keeping them in sync.
  - other frameworks like SHACL may be used for a frame-independent representation of the RDF.

## Resources

- https://www.linkedin.com/groups/14303246/
- [LinkML: an open data modeling framework, grounded with ontologies](https://lnkd.in/gZv2TU6E)
  - [[p.mentioned]] [[prdct.knowledge-graph-change-language]]
- [[c.resource.learning]] 
  - https://linkml.io/linkml/intro/tutorial.html
  - https://github.com/linkml/linkml-tutorial
- https://github.com/w3c/wot-thing-description/blob/egekorkan-patch-3/toolchain/tool-analysis.md