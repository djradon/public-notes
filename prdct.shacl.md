---
id: ahbj9ejugov8rjiywj5qqc8
title: Shacl
desc: 'designed for validating RDF data against a set of constraints (shapes)'
updated: 1721768988988
created: 1706306106639
---

![[prdct.rdf-js.shex#^1vgrpmk2ihl1]]
- "SHACL uses RDFS subclassing mechanism. When you create SHACL models you define classes and more specific subclasses. Additionally, you can separate Node Shapes from classes to define application specific views.Take a look at [this blog](https://www.topquadrant.com/classes-and-node-shapes-when-to-separate/) to understand differences between classes and node shapes... With SHACL, you can deactivate constraints that you don’t need or can’t agree with. This is done declaratively, using the standard so it is unambiguously clear what aspects of the models you are using and what aspects you are not using."
- "SHACL is a semantic constraint language, which is quite useful as a guard for updates to a triple store. Because SHACL is less concerned with meaning and more concerned with structure, many object-oriented ontologists prefer it to OWL for defining their classes."
- SHACL was strongly influenced by [[prdct.spin]] and can be regarded as its legitimate successor
- "Shacl popped up because people wanted to have something that operstes over their A-Boxes without slowly dragging their entire modeling and data storage into the T-Box. That's why they don't want the "description logic perspective", as it automatically leads down that "no instances, just theories" rabbit hole."


## Examples

- https://archive.topquadrant.com/edg-ontologies-overview/
  - "If a group of properties is reusable across assets that are not subclasses of each other (e.g., enterprise, technical and data assets are not subclasses of each other), EDG ontologies define an aspect class to hold or comprise this group of properties."
  - mentions [[t.cs.semantic-web.aspect-classes]]

## Constraint Types

-   **Structural Constraints**: Ensuring that data adheres to a specific schema or model, such as required properties, permissible property values, or specific class hierarchies.
-   **Value Constraints**: Limiting the values that can be taken by properties, including data types, value ranges, and pattern matching.
-   **Cardinality Constraints**: Defining the minimum and maximum occurrences of properties.
-   **Logical Constraints**: Applying logical conditions to properties and values, such as equality or inequality, and combinations thereof through logical operators.

## Comparisons

![[prdct.rdf-js.shex#shex-vs-shacl]]

![[prdct.spin#spin-vs-shacl]]

## Resources

- https://archive.topquadrant.com/shacl-blog/
  - "There are many ontologies in OWL which are really glossaries or taxonomies of terms. They do not define classes in terms of properties of their members. In other words, they do not contain schema or data definitions. They simply describe classes as vocabulary terms. You can easily identify such “ontologies” because you will see no OWL restrictions or domain/range statements. Instead, you will see synonyms and other annotation properties. In this case, recognize them for what they are and translate them to [[prdct.skos]] and/or develop a small ontology of your own to express this information. There is no value in keeping these terminologies in OWL nor in having them in SHACL."

## References

- https://tdan.com/the-data-centric-revolution-best-practices-and-schools-of-ontology-design/31412
- https://news.ycombinator.com/item?id=31890041
- [[ar.topquadrant.why-i-dont-use-owl-anymore]]
- https://www.ontotext.com/knowledgehub/fundamentals/what-is-shacl/
- https://medium.com/fluree/what-is-shacl-with-examples-2697f659d465
- https://connect-lokesh.medium.com/demystifying-shacl-guide-to-semantic-validation-part-1-016aa65d2070
- [[ar.topquadrant.why-i-use-shacl-for-defining-ontology-models]]
- [[ar.hackernews.semantic-web-is-like-the-guy-that-tells-everyone-that-he-is-an-asshole]]