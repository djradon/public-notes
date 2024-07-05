---
id: x4h93xhzc9ab85h4x3tlfko
title: Class Vs Individual
desc: 'aka metaclasses vs superclasses'
updated: 1720210138414
created: 1716575654799
---

- in addition to [[book.semantic-modeling-for-data#class-or-individual]], there's:

## Fourth Option

- use one of the class annotation properties, e.g.
  - rdfs:comment, rdfs:seeAlso, rdfs:isDefinedBy, or
  - a custom annotation defined with owl:AnnotationProperty
    - used to add additional information to classes, properties, or individuals without affecting the logical structure of the ontology.
      - t.2024.05.25.14 well, kinda

### AnnotationProperty example

## Thoughts

- "Punning is a simple way to provide for metamodeling that (a) does not require a major change to OWL 1.1 (DL) reasoners and (b) usually seems to satisfy the semantic requirements."

## Resources

- [[ar.onto-clean-in-owl-with-a-dl-reasoner-a-tutorial]]

## References

- https://www.w3.org/2007/OWL/wiki/Punning
- https://stackoverflow.com/questions/38208212/does-owl-punning-treats-class-and-individual-with-same-name-as-same-semantically
- https://lists.w3.org/Archives/Public/semantic-web/2011Jun/0245.html