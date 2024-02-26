---
id: n3rurtjfaiyv6jlx4qnevsc
title: AML
desc: 'Anything Modeling Language is a declarative language for defining metadata documents that can be parsed into graphs of information. These documents can be published and linked on the web or through any other type of API.

It can be used to describe common, existing YAML/JSON metadata documents or to define the semantics and structure of completely new metadata formats.'
updated: 1708975952631
created: 1701289941576
docs: https://a.ml/docs/aml/aml
related: "[[prdct.amf]]" 
---

## Features

- "AML enables you to formally describe different kinds of models, whether syntactic models—specific to languages or specifications-or semantic models specific to industries and domains."
- "a.ml: Anything Modeling Language... which targets mapping of YAML schemas to ontologies and SHACL shapes, and YAML documents to RDF graphs." 
  - https://platform.ontotext.com/3.4/soml/intro.html

## Terms

Dialect
: defines a set of constraints over a RDF data-model composed by a graph of nodes connected by properties. All node types and properties have associated terms that must have been defined in a AML Vocabulary. Additionally, the AML Dialect also defines a mapping of this nodes over a set of modular documents (including partial definitions encoded in fragments and libraries of reusable components), that encode a mapping function capable of transforming document instances of the dialect encoded in YAML or JSON documents into RDF graphs encoded in JSON-LD documents.

Vocabulary
: a mechanism to describe any domain of discourse using familiar YAML syntax and modular documents.

## Resources

- https://github.com/aml-org/als/blob/develop/readme.md 
  - "You can adapt the Microsoft VSCode LSP example by following these instructions, which guides you to successfully run an ALS client in VSCode."