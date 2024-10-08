---
id: x4h93xhzc9ab85h4x3tlfko
title: Class Vs Individual
desc: aka metaclasses vs superclasses
updated: 1725898374816
created: 1716575654799
---

- aka: [[t.phil.type-token-distinction]] 
- Superclasses/supertypes define inheritance relationships between classes or types.
- Metaclasses/metatypes classify classes
- powerclasses/powertypes define properties of their classes/types; i.e. a class that classifies types of a given class, focusing on distinguishing between subclasses 
  - [[prdct.unified-foundational-ontology.gUFO]] has gufo:Type which is the powerclass 

## Definitions

- Only classes have superclasses, while other classifiers have supertypes.
  - Since Class is also a Classifier, a superclass is always a supertype
- powertype is a type whose instances are themselves types.

## Conclusion

- t.2024.07.11.09 after trying to formulate a comment for [[ar.medium.mike-dillinger.the-nature-of-knowledge-graph-predicates]], I feel a small a-ha!
  - Data Scientist, as a sub-class of Occupation, requires that all its instances are occupations
- 2+: 

## Issues

- just like my Dendron notes, do we have separate classes for things, or can concepts just double as classes?
  - based on my experience, it's better to just have one class/concept/universal, but can be aliased from multiple places
    - t.2024.09.09.09 thinking about this more in 

### Classes as Values

#### Approach 3: Create a parallel hierarchy of instances as property values

- rdfs:seeAlso

- in addition to [[book.semantic-modeling-for-data#class-or-individual]], there's:

## Second Option + Linking Annotation

- aka "Create a parallel hierarchy of instances as property values"
- use one of the class annotation properties, e.g.
  - rdfs:comment, **rdfs:seeAlso**, rdfs:isDefinedBy, or
  - a custom annotation defined with owl:AnnotationProperty
    - used to add additional information to classes, properties, or individuals without affecting the logical structure of the ontology.
      - t.2024.05.25.14 well, kinda

### AnnotationProperty example

## Fourth Option: Using annotations as (non-logical) properties

- maybe losing reasoning isn't important?
  - transitive might be important,
    - e.g.
      - CharacterClassChoice shouldOccurBefore CharacterAbilityScoreChoice
      - CharacterAbilityScoreChoice shouldOccurBefore CharacterSkillChoice
      - 
 

## Thoughts

### Punning

- "Punning is a simple way to provide for metamodeling that (a) does not require a major change to OWL 1.1 (DL) reasoners and (b) usually seems to satisfy the semantic requirements."
- "An IRI I can be used in an OWL 2 ontology to refer to more than one type of entity. Such usage of I is often called metamodeling, because it can be used to state facts about classes and properties themselves. In such cases, the entities that share the same IRI I should be understood as different "views" of the same underlying notion identified by the IRI I."

## Resources

- [[ar.onto-clean-in-owl-with-a-dl-reasoner-a-tutorial]]

## References

- https://www.w3.org/2007/OWL/wiki/Punning
- https://stackoverflow.com/questions/38208212/does-owl-punning-treats-class-and-individual-with-same-name-as-same-semantically
- https://lists.w3.org/Archives/Public/semantic-web/2011Jun/0245.html
- https://www.w3.org/TR/swbp-classes-as-values/
- [[ar.towards-ontological-foundations-for-conceptual-modeling-the-unified-foundational-ontology-ufo-story]]
- [[ar.an-extensible-approach-to-multi-level-ontology-modelling#^vt540o589i6g]]