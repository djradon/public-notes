---
id: nfwxllOsJ5Xne268kb784
title: Class vs. Type
desc: ''
updated: 1633320178004
created: 1633200115228
---
- in RDF, "type" is the class of an instance; Sub-classes can be said to be types of Classes but better to use subClassOf, e.g.:
  - Car hasSubclass Ford #preferred
  - Car type Ford #discouraged
  - My old mustange type Ford #preferred 

- [RDF Core Schema](https://www.w3.org/2001/sw/RDFCore/Schema/20010618/) says "type" states that a resource is an instance of a class
- type is problematic in informal speech; can mean instance of a class OR subClass of a Class
  - e.g. Ford is a type of car, but Mustang is a type of Ford and convertible is a type of Mustang
    - Ford is a type of car manufacturer though
- type feels a little less formal, but outside of programming they mean pretty much the same thing


## Resources

- https://dev.to/awwsmm/types-vs-classes-39an
  - [[pred.hasContext]] [[t.programming]]
