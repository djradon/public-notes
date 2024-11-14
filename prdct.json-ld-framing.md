---
id: 1nc1g14pq1wpjdsqx3lr7pw
title: JSON-LD Framing
desc: 'allows developers to query by example and force a specific tree layout to a JSON-LD document.'
updated: 1731604586677
created: 1731604245762
---

- https://www.w3.org/TR/json-ld-framing/

## Description

- A Frame can be used by a developer on a JSON-LD document to specify a deterministic layout for a graph... such that statements about a particular subject are bundled together, delimited via { and }, and such that the subjects they relate to "nest" into a particular tree structure that matches what their application expects.

## Example

When using a flattened set of objects that match the frame components:
Example 3: Flattened library objects

```json
{
  "@context": {
    "@vocab": "http://example.org/",
    "contains": {"@type": "@id"}
  },
  "@graph": [{
    "@id": "http://example.org/library",
    "@type": "Library",
    "location": "Athens",
    "contains": "http://example.org/library/the-republic"
  }, {
    "@id": "http://example.org/library/the-republic",
    "@type": "Book",
    "creator": "Plato",
    "title": "The Republic",
    "contains": "http://example.org/library/the-republic#introduction"
  }, {
    "@id": "http://example.org/library/the-republic#introduction",
    "@type": "Chapter",
    "description": "An introductory chapter on The Republic.",
    "title": "The Introduction"
  }]
}
```

The Frame Algorithm can create a new document which follows the structure of the frame:
Example 4: Framed library objects
Open in playground

```json
{
  "@context": {"@vocab": "http://example.org/"},
  "@id": "http://example.org/library",
  "@type": "Library",
  "location": "Athens",
  "contains": {
    "@id": "http://example.org/library/the-republic",
    "@type": "Book",
    "creator": "Plato",
    "title": "The Republic",
    "contains": {
      "@id": "http://example.org/library/the-republic#introduction",
      "@type": "Chapter",
      "description": "An introductory chapter on The Republic.",
      "title": "The Introduction"
    }
  }
}
```
