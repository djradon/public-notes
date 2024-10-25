---
id: c5qcd8cate4ic318mkmmkn0
title: Kosmion 
desc: 'a new approach to the semantic web'
updated: 1729889472632
created: 1729094754216
---

## Description

The Kosmion ontology is designed with a human-first orientation and a domain-first approach that allows data modelers to define their own top-level constructs and hierarchies rather than fitting them into a predefined universal structure. 

But if you're already using an upper ontology, it can work with that too.
      
Kosmion is intended to be a utilitarian foundational ontology, advocating for “relator-atoms,” also known as [[t.cs.semantic-web.relationship-to-entity-conversion]], as an alternative to traditional properties/relations. This approach allows:

- relevant facets instead of instantiating traditional classes.
- n-ary relations, including unary relations
- system-time (with kosm:relator-genesis, kosm:relator-tombstone, and kosm:relator-successor)
- immutability and attribution for lineage, auditing, and time-travel purposes
- “statements about relators”, and since any traditional RDF statement can be expressed with a relator (I think), it could be considered an alternative to RDF-star, which aims to support “statements about statements”
- contexts for specifying alternate realities and other less-truthy perspectives
- **Multi-perspective Modeling**: By using relators for every connection, it becomes possible to represent different perspectives or interpretations of the same entities, allowing richer semantic descriptions and supporting use cases like storytelling, versioning, or conflicting viewpoints.
- maybe: relations that may involve either a datatype property or an object property as their object, or both 

Kosmion is intend to use “OWL2 Full” (i.e., the RDF-based semantics), which supposedly might mean it's undecideable and unreasonable. It's also unorthodox, so probably breaks a lot of tooling. Tough luck computers.

Arguably, relators are also less readable and more complicated than classic RDF triples. Sorry about that, humans. At least the expressiveness is decent.
