---
id: 6bws0tqddjcgazi71cxrhvk
title: Linkset
desc: 'collection of triples whose subject and object are described in different datasets'
updated: 1721604603876
created: 1721604546889
---

## Description

A linkset is a collection of such RDF links between two datasets. It is a set of RDF triples where all subjects are in one dataset and all objects are in another dataset. RDF links often have the owl:sameAs predicate, but any other property could occur as the predicate of RDF links as well.

In VoID, a linkset is modelled as an instance of the void:Linkset class. void:Linkset is a subclass of void:Dataset.

## References

https://www.w3.org/TR/void/#dataset