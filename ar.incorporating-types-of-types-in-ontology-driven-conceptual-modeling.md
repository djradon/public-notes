---
id: irpbecuanb3c1sa3fa2q23m
title: Incorporating Types of Types in Ontology Driven Conceptual Modeling
desc: extends UFO with support for multi-level classification
updated: 1728755739297
created: 1724872032986
---

- https://nemo.inf.ufes.br/wp-content/papercite-data/pdf/incorporating_types_of_types_in_ontology_driven_conceptual_modeling_2022.pdf
- authors: @claudenir-fonseca @giancarlo-guizzardi @joao-paulo-almeida @tiago-prince-sales @daniele-porello
- topics: [[t.cs.sd.modeling.conceptual-modeling.ontology-driven]] [[t.km.ontology.multi-level-theory]] [[prdct.ontouml]]
- published: t.2022-10

## Abstract

The Unified Foundational Ontology ([[prdct.unified-foundational-ontology]]) has been used to provide foundations for the major conceptual modeling constructs. So far, UFO has reflected a view in which domain entities are fundamentally divided into those that collect invariants of the domain (i.e., types) and those entities that manifest those invariants (i.e., instances), following the conventional two-level classification scheme. This paper extends UFO with support for multi-level classification schemes, in which some entities accumulate both type-like and instance-like characteristics. This requires an ontological interpretation and a formal theory of types of types. This theory is employed to engineer new constructs and constraints into the OntoUML language, and to develop computational support for the formal verification of constraint violation over multi-level conceptual models.


## Highlights

### Introduction

- in a multitude of domains, entities that accumulate both type-like and instancelike characteristics play a central role
  - e.g.,  in biological taxonomy, the type
Canis familiaris collects the properties manifested in individual dogs (e.g., having fur,
being quadrupeds) while manifesting itself properties of the type Species (e.g., having
a certain biological origin, having an expected lifespan). In other words, in this domain, we are concerned not only with types of individuals (i.e., first-order types), but also with types of types (i.e., high-order types)
- This paper extends UFO and then OntoUML with support for multi-level modeling, including an ontological interpretation and formal model of high-order types
- A distinctive feature of our approach is that, by considering types as endurants, we can account for qualitative changes that these types may undergo in time ^18mad1ssk2w1
- This means that the UFO ontological categories applicable to types of individual endurants (such as kinds, phases, roles, etc.) [22] also apply to types of types
  - For instance, in biology, this allows us to account for high-order types such as Endangered Species or Extinct Species as phases, as the very same species can instantiate these types in different situations
- Treating types as endurants also allows us to account for temporal properties of their existence:
    - particularly important for types such as social roles, artifactual types, and nominal kinds in general

### Background and Motivation

