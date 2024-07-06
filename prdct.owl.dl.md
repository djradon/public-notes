---
id: 5dggkb9889axpi4uzlbsdxm
title: OWL-DL
desc: 'decideable'
updated: 1720225370101
created: 1718171299666
---

## Gotachas

- The sets of object properties, datatype properties, annotation properties and ontology properties must be mutually disjoint. Thus, in OWL DL dc:creator cannot be at the same time a datatype property and an annotation property.
  - ? so you would use an alternate suffix? Guessing that prefixing can work for single resources
  - 


## Effective Use

### Insight 1: Concept vs Aspect

OWL defines a thing called Class; a Class is a set of individuals. We use Class to define things like Requirement and Interface. Although it’s implicit, what we mean when we define classes like Requirement and Interface is that nothing can be both a Requirement and an Interface. In OWL, if that’s what you mean, you have to say it, either explicitly

```
DisjointClasses(:Requirement :Interface)
```

or implicitly via incompatible constraints.

We also use Class to define things like IdentifiedThing and AggregatedThing. In this case we do not mean that nothing can be both; it makes perfect sense for an aggregate to have an identifier. OWL gives us the low-level tools to distinguish between these use cases, but in practice it is tedious and error-prone to manage large taxonomies with only low-level tools.

In our practice we distinguish between what we call a Concept (e.g., Requirement, Interface) and what we call an Aspect (e.g. IdentifiedThing, AggregatedThing). For Concepts we apply a disjointness management policy that generates disjointness axioms by machine reasoning. For Aspects we do not. Formalizing this distinction has dramatically reduced the effort and error risk of managing taxonomies.

We have five such distinct use cases for OWL Class.

### Insight 2: Object Property Reification

In OWL we can say a camera acquires an image like this

```
ObjectPropertyAssertion(:acquires :camera :image)
```

The assertion itself has no identity, which means we can’t say anything about it. It would be useful, however to be able to express “Requirement _R.x.y_ specifies that the camera shall acquire an image”, i.e., to state a functional requirement. It’s possible, using a technique called reification, to create a named individual to represent the condition that the camera acquires an image in such a way that implies the assertion above–in which a reasoner will conclude that. Because the reification itself has an identity, and we can make that the target of another assertion like this

```
ObjectPropertyAssertion(:specifies :R.x.y :camera_acquires_image)
```

This reification technique is extremely useful and we have incorporated it into our practice; nearly every relationship is reified.

There’s nothing particularly deep about reification. It’s using the standard expressivity of OWL in a repeatable pattern to convey the meaning we want. But it is, again, tedious and error-prone to do manually.

## References

- https://www.opencaesar.io/blog/2021/06/19/OML-Origin-and-Rationale.html