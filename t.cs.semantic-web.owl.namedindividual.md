---
id: kfm768wswqk5s7pkti4kwud
title: Namedindividual
desc: ''
updated: 1729635010402
created: 1729634949678
---

- owl:NamedIndividual is used as a declaration. As such, it does not affect reasoning and serves only to check that a particular entity is used in accordance with how it was declared. This is not important much when you use the RDF-based semantics (and in OWL 2 Full, it is the same class as owl:Thing), but OWL 2 DL distinguishes between named (using IRI) and anonymous (using bNode) individuals, and some profiles of it even disallow anonymous individuals completely.
- Protegé here does its best to ensure that the ontology is acceptable in the various lower profiles, by marking declarations based on the way they are identified, but it is not strictly an error if you do something like _:bnode a owl:NamedIndividual . ‒ you may use that to convey that it really is a proper individual that has an (unknown) IRI, as opposed to an existential quantifier-like notion used by RDFS.

## References

- https://stackoverflow.com/questions/77016188/why-does-prot%C3%A9g%C3%A9-add-owlnamedindividual-as-rdftype-for-each-instance-that-has