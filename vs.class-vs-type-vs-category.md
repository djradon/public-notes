---
id: nfwxllOsJ5Xne268kb784
title: Class vs. Type vs. Category
desc: ''
updated: 1728927677501
created: 1633200115228
---

## Definition

- a category is an intensional set (specifying necessary and sufficient conditions) with criteria for defining membership. A class is an extensional set where membership is explicitly asserted and specific properties can be defined as necessary.

### [[prdct.rdf]]

- in RDF, "type" is the class of an instance; Sub-classes can be said to be types of Classes but better to use subClassOf, e.g.:
  - Car hasSubclass Ford #preferred
  - Car type Ford #discouraged ^VCeEIajzeBga
  - My old mustange type Ford #preferred 

- [RDF Core Schema](https://www.w3.org/2001/sw/RDFCore/Schema/20010618/) says "type" states that a resource is an instance of a class
- type is problematic in informal speech; can mean instance of a class OR subClass of a Class
  - e.g. Ford is a type of car, but Mustang is a type of Ford and convertible is a type of Mustang
    - Ford is a type of car manufacturer though
- type feels a little less formal, but outside of programming they mean pretty much the same thing

### https://www.cerritos.edu/dwhitney/SitePages/CIS201/Lectures/IM-7ed-Chapter04.pdf

 A class is a category or classification used to describe a set of objects. So a class is a
category, but it is also a set of objects. 


## Resources

- https://dev.to/awwsmm/types-vs-classes-39an
  - [[p.hasContext]] [[t.cs.programming]]
- [[Discussion|p.instanceOf#discussion]]

- https://www.cerritos.edu/dwhitney/SitePages/CIS201/Lectures/IM-7ed-Chapter04.pdf
- https://www.semanticarts.com/wp-content/uploads/2018/10/CategoriesandClassesDMc060515newtemplate.pdf
  - [[ar.ontologist.classes-categories-types-and-shapes]]