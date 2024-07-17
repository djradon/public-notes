---
id: 6k9uhp5xoexn6ok8uxaty0b
title: Ordered Turtle Serializer
desc: 'extension to the rdflib Turtle serializer that adds order'
updated: 1721155110971
created: 1721154201412
---

- https://github.com/scriptotek/otsrdflib
- dead
- written-in: python

## Features

- classes are ordered alphabetically by their URIs.
  - custom order can be imposed by adding classes to the class_order attribute. For a SKOS vocabulary, for instance, you might want to sort the concept scheme first, followed by the other elements of the vocabulary
- instances of a class are ordered alphabetically by their URIS.
  - custom order can be imposed by defining functions that generate sort keys from the URIs. For instance, you could define a function that returns the numeric last part of an URI to be sorted numerically
- 