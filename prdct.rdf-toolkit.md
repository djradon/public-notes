---
id: xfgsz06xqzrfizxkhvghgma
title: Rdf Toolkit
desc: 'RDF Serializer, to be used in a git commit-hook to force automatic correct rewrite of every OWL ontology '
updated: 1716323153620
created: 1716322742260
---

- repo: https://github.com/edmcouncil/rdf-toolkit
- [[c.software.semantic]]
- written-in: java


## Rationale

### Minimize the ontology review effort

For the purposes of git-based version control of ontology files, we want to have as few differences between commits as possible. Most ontology editors can encode RDF graphs, including OWL ontologies, in several formats, including the W3C normative RDF exchange formats (syntaxes): RDF/XML and Turtle. However, even these normative formats are not canonical. Therefore, an editor tool may change many aspects of how ontology entities are serialized every time the ontology is saved (such as adding/changing comments or changing the order and organization of statements) leading to difficulties in analyzing actual changes in the underlying semantics.

### Handle intelligent IRIs

We want to be able to include actionable information as part of IRIs, e.g., git tags, and then deference them from ontology tools like Protege.

### Recommended output format

The recommended output format at this time is RDF/XML because that is the format that the OMG requires for submissions. The EDM Council develops the FIBO Ontologies and submits them as RDF/XML, serialized by the RDF Toolkit to the OMG. So that is why we also use RDF/XML in Github itself.