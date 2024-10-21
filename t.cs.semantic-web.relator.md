---
id: aqlimlaytofoqkt8f23z9cn
title: Relator
desc: 'an intermediary entity that connects or relates other entities through specific relationships'
updated: 1729504763577
created: 1721858229634
---

- aka: [[Relationship to Entity Conversion|ar.valid-time-rdf#relationship-to-entity-conversion-rec]]

## Features

- allows all n-ary relationships
  - even so-called unary relationships like "Dave walked" can be expressed, e.g.
```turtle
:dave-walking a :walking-relationship;
  :walker :dave;
  :tense :past-tense

```

## Issues

- "If modelling relationships as classes is useful, then why not use this pattern for all non-trivial relationships in a model? The main reason is that it causes explosion in the number of terms in a vocabulary, e.g. each predicate is replaced with two predicates and a class. A vocabulary can quickly become unwieldy, so the value of the extra modelling structure needs to be justified with clear requirements for needing the extra complexity. As described here, the primary reason is to qualify the relation." 

## Implementations

- https://bioportal.bioontology.org/ontologies/GFO?p=classes&conceptid=gfo%3ARelator
- https://nemo-ufes.github.io/gufo/#Relator
- https://patterns.dataincubator.org/book/qualified-relation.html

## References

- https://ontouml.readthedocs.io/en/latest/classes/sortals/relator/index.html