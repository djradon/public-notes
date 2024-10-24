---
id: krnhgkluk239voicao4aphu
title: Ordered Data in Rdf
desc: ''
updated: 1729803657525
created: 1729803152244
---

- https://ontola.io/blog/ordered-data-in-rdf

## Highlights

- json-ld arrays are rdf:List

### tl;dr

**RDF Containers:**

-   Come in three forms: `rdf:Seq` (ordered), `rdf:Bag` (unordered), `rdf:Alt` (alternatives with default)
-   You can add new items by simply adding RDF triples
-   Inserting items is hard: requires rewriting _many_ statements
-   Must be stored in a single graph / machine / server (centralized)
-   Have a formally unknown ending (open world assumption)

**RDF Collections:**

-   An ordered chain of `rdf:List` resources
-   You have to edit / remove statements before you can add new items
-   Inserting items is easy: requires changing _just a few_ statements
-   Can span many graphs / machines / servers (decentralized)
-   Have a known ending (the `rdf:nil`)