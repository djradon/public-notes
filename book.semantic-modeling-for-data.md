---
id: uup0x4gcs3ilsku9xbw4xcx
title: Semantic Modeling for Data
desc: ''
updated: 1698168270855
created: 1698168250108
---

- url: https://learning.oreilly.com/library/view/semantic-modeling-for/9781492054269/

## Highlights

- Based on these definitions, what do you understand to be a concept in a semantic model? Is it a set of things as the Protégé tutorial suggests, or some unit of thought as SKOS claims? And what should you do if you need to model a concept in OWL that is not really a set of things? Should you still have to make it a class? The answer, as we will see in the rest of the book, is that the SKOS definition is more accurate and useful, and that the “concept = class” claim of the OWL tutorial is at best misleading, causing several semantic modeling errors that we will see later in the book.
dave
particulars
dave
; a concept can indeed play the role of a class if its definition implies a set of entities that instantiate it, but this is not always the case.
In property graphs, for example, there is no formal distinction between a class and an instance since everything is a node (node labels can play the role of a class but not exclusively
in OWL, entities that can be classes are often modeled as individuals because, otherwise, they cannot be related to other entities
dave
Lexical variants differ from synonyms in that synonyms are different terms for the same entity, while lexical variants are different word forms for the same term.