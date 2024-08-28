---
id: 4p9syg1oz2pe0e78c8ry8gq
title: OntoUML
desc: ''
updated: 1724877048127
created: 1709679259786
---

- related: 
  - [[prdct.ontouml-vp-plugin]] 
  - https://ontouml.org/ (dead on arrival)

## Issues

- difficult to translate into OWL, given meta-modeling

## Theory

### Types/Classes

- Some types have the characteristic of providing identity principles for their instances. They are stereotype as: «Kind», «Collective», «Quantity», «Relator», «Mode» and «Quantity»
- other types don’t provide identity principle for their instances, but they all share a common one. They are stereotyped as: «Subkind», «Role» and «Phase»
- other types don’t provide identity and their instances follow different identity principles. They are stereotyped as: «RoleMixin», «Mixin» and «Category»

## Class Stereotypes

### Kind


### Subkind


### Phase

- an anti-rigid, sortal concept that applies to an entity during a particular stage or phase of its existence

### Role


### Collective


### Quantity


### Relator

- "The «Relator» construct is used to represent truth-makers of material relations, i.e., the “things” that must exist in order for two or more individuals to be connected by material relations. Because of this nature, relators are always dependent on other individuals to exist."

### Category


### PhaseMixin

- equivalent of «Phase» for types that aggregate instances with different identity principles
- A class stereotyped as «PhaseMixin» is also an anti-rigid type
- similar semantically to «RoleMixin» with the difference in relational dependency

### RoleMixin

- the equivalent of «Role» for types that aggregate instances with different identity principles
- A class stereotyped as «RoleMixin» is also an anti-rigid type whose instantiation depends on a relational property
- e.g.,: customer, provider, purchased, resource
- usually occur in one of the two patterns:
  - defined by roles
  ![](/assets/images/2024-08-28-13-28-32.png)
  - as a role of category
  ![](/assets/images/2024-08-28-13-29-24.png)
  - The second pattern is a more concise form of the first. They are semantically equivalent.
- always abstract
- 

### Mixin


### Mode


### Quality



## Relationship Stereotypes

### Formal

- short for Domain Comparative Formal Relation
- represents relations that can be reduced to the comparison of the quality values that characterize the related individuals
  - like heavier-then, younger-then or cheaper-then
  - 

### Material

- have material structure on their own and include examples such as employments, kisses, enrollments, flight, connections and commitments
- Material relations are derived (via «Derivation») from relators and the mediation relations that connect them to the corresponding relata
- several «Material» relations can be derived from a single «Relator» and «Mediation» relations

### Mediation

- a relation of «Mediation» between a «Relator» and the entities it connects
- a type of existential dependence relation (a form of nonfunctional inherence)
- can be derived from the relation between the relata and the qua individiuals that compose the relator and that inhere in the relata
- must mediate at least two distinct individuals.

### Characterization

- a relation between a bearer type and its feature
- Feature is intrinsic (inherent) moment of its bearer type, and thus existentially dependent on the bearer
- Feature may be stereotyped as «Quality» or «Mode»
- Feature characterizes a bearer type iff every instance of bearer exemplifies the feature.

### Derivation


### Structuration


### Part-Whole


### ComponentOf


### Containment


### MemberOf


### SubCollectionOf


### SubQuantityOf




## References

- [^1]: https://ontouml.readthedocs.io/en/latest/classes/sortals/relator/index.html
- [[ar.using-a-trope-based-foundational-ontology-for-bridging-different-areas-of-concern-in-ontology-driven-conceptual-modeling]]