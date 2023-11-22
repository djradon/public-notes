---
id: 61vfsxkoprebg1j1zjmekn8
title: Markdown-LD
desc: 'RDF Linked Data in Markdown'
updated: 1698320046488
created: 1698319884858
---

- repo: https://github.com/ozekik/markdown-ld
- #eg https://ozekik.github.io/markdown-ld/

## Specification

A Markdown-LD document MUST have a level-1 heading which represents the name of the graph described under the heading.

Level-1, level-2, and level-3 headings MUST be immediately followed by a line of inline code for its RDF term in Turtle syntax.

A pair of a heading and a line of inline code is called _Markdown-LD heading_.

A level-1 Markdown-LD heading MAY be immediately followed by a code block for `@base` and `@prefix` directives and other implicit RDF triples in Turtle syntax.

Until the next heading, Markdown texts after the code block are treated as comments.