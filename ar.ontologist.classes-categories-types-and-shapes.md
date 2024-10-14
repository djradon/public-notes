---
id: 1d5epycjkdnj9kvdx8n6h5e
title: Classes Categories Types and Shapes
desc: ''
updated: 1728930322788
created: 1728927678409
---

- https://ontologist.substack.com/p/classes-categories-types-and-shapes

## Summary

- "an instance describes a given entity describing relevant characteristics (properties + values), while a class is an abstraction of that entity describing relevant properties alone."
  - t.2024.10.14.10 what?! posted a request for clarification.
- bottom-up approach - the subordinate class or concept is the originator of the relationship (in the subject or first position), and the superordinate class or concept is in the right-hand position.

### category vs class

What differentiates a category from another class is that the instances of that class are themselves classes:

```turtle
Category: rdfs:subClassOf rdfs:Class .
Domestication: a Category: .
Domestication:Wild a Domestication: .
```

This relationship is different than for entities:

```turtle
Entity: a rdfs:Class .
Animal: rdfs:subClassOf Entity: .
Animal:Fox a Entity: .
```

This distinction is subtle but important. Entity classes are specialized through subclass inheritance (an `Animal:` and a `Fox:` are both entities with a `Fox:` being a specialized kind of `Animal`:) and can be quite deep. Categories generally have a few broad specializations (such as units or enumerations), but are typically quite shallow.