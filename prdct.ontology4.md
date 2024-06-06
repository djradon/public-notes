---
id: qp2otr2le1jgejqw0f828qk
title: Ontology4
desc: 'a superset ontology'
updated: 1717701627216
created: 1717691191480
---

- https://ontology4.us/

## Interesting

- In contrast to Resource_Description_Framework|RDF as standard model für data interchange on the Web, Ontology4 uses quadrupels instead of triplets and adds the time dimension for every relation between subjects and objects.
- Ontology4 provides standardized notation for subjects/objects (^), relations (<>), instances (>), methods (°) and verbs/activities (~). Each of the symbols has its own graphical symbol in the semantical net graphs.
- PQL (Predicate Query Language) translates to OQL (Ontology Query Language)

### Dualism

- **Class-Attribute Dualism** has two approaches
  - 1. class has a property, and instances are members of class
    - e.g.: particularPerson is a Person, and has gender
  - 2. subclasses of a class have restrictions, and instances can be members of both classes
    - e.g.: particularPerson is a MalePerson and FemalePerson
  - "But only the second approach allows to model hermaphrodites by letting an instance >Instance-H1 be instance of the subclasses ^Class-F and ^Class-M at the same time. In the first approach, this can not be done, since then the attribute .Attribute-G would have to have the two values male AND female for >Instance-H1 like"
    - t.2024.06.06.09 but really? 

### 4 dimensions


    classes are represented by red ovals,
    relations are represented by dark blue octagons and
    activities are represented by yellow houses.
    instances are presented by green houses.

### Taxoverbies

- hierarchies of verbs/activities
- They parallel taxonomies as hierarchies of classes and mereologies as hierarchies of compositions/part-wholes.

## References

- https://ontology4.us/english/Ontologies/Upper-Ontologies/Concepts_Comparison/index.html