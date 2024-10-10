---
id: 4p9syg1oz2pe0e78c8ry8gq
title: OntoUML
desc: ''
updated: 1728409846736
created: 1709679259786
---

- related: 
  - [[prdct.ontouml-vp-plugin]] 
  - https://ontouml.org/ (dead on arrival)
  - https://dev.ontouml.org/ "documentation for"
  - [[prdct.ontouml-ufo-catalog]]

## Issues

- difficult to translate into OWL, given meta-modeling

## Theory

### Identity Principle

- needs to apply to everyone, e.g. no SSN
- "every individual must have exactly one. So, what is the identity principle for a person? One’s fingerprint, iris pattern, DNA? Well, it is really hard to define it, even though we know it is there."
- Some types have the characteristic of providing identity principles for their instances. They are stereotype as: «Kind», «Collective», «Quantity», «Relator», «Mode» and «Quantity»
- other types don’t provide identity principle for their instances, but they all share a common one. They are stereotyped as: «Subkind», «Role» and «Phase»
- Some other types don’t provide identity and their instances follow different identity principles. They are stereotyped as: «RoleMixin», «Mixin» and «Category». Here are some examples:



## Class Stereotypes

### Kind

- represent rigid concepts that provide an identity principle for their instances and do not require a relational dependency
  - When we say that a «Kind» is relationally independent, we mean that it does not necessarily require a relation to be defined, like a «Role» does
    - e.g. from [[prdct.software-requirements-reference-ontology-srro]]
- represent a Functional Complex, i.e., a whole that has parts contributing in different ways for its functionality
- e.g.: human body, forest, computer, key, car, organization

### Subkind


### Phase

- an anti-rigid, sortal concept that applies to an entity during a particular stage or phase of its existence

### Role


### Collective


### Quantity


### Relator

- "The «Relator» construct is used to represent truth-makers of material relations, i.e., the “things” that must exist in order for two or more individuals to be connected by material relations. Because of this nature, relators are always dependent on other individuals to exist."
- e.g.: Marriage, Investigation, Enrollment, Employment, Subscription
- the «Relator» meta-class is analogous to the «Kind», «Collective» and «Quantity» meta-classes, in the sense that it is rigid and provides an identity principle for its instances.
  - The difference is that, instead of representing functional complexes, quantities or collections, a «Relator» represents the objectification of relational properties
  - relators can also be specialised by subkinds, phases and roles, and generalised by categories and mixins
- A «Relator» must always be connected (directly or indirectly) to at least one relation stereotyped as «Mediation»
- "The sum of the minimum cardinalities of the opposite ends of the mediations connected (directly or indirectly) to the «Relator» must be greater or equal to 2."
  - but why?



### Category

- a rigid mixin that does not require a dependency to be specified
- abstract class that generalizes across multiple kinds.
  - "essential characteristics that are shared by different kinds but do not directly instantiate entities."

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
  - They define characteristics that apply across multiple kinds but are not directly instantiated.

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
- https://ontouml.readthedocs.io/en/latest/theory/identity.html#identity