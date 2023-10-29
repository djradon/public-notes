---
id: TIehWkHNVWQJk4RFT5EBX
title: Property Graph
desc: ''
updated: 1698526999202
created: 1638293019662
---



- [[p.hasSpecification]] [[prdct.ngsi-ld]]
- [[p.hasVariant]] [[t.km.knowledge-graph.lpg]]

## vs [[prdct.rdf]]

- http://www.snee.com/bobdc.blog/2018/04/reification-is-a-red-herring.html
  - In RDF, "if you want to keep track of separate instances of a particular relationship, declare a class for that relationship and then create instances of it."

## vs [[prdct.RDF-star]]

- https://opencredo.com/blogs/making-sense-of-data-with-rdf-vs-lpg/
  - "In property graphs, attribute values are just strings not linked to any other nodes in the graph. They can only represent literal values, rather than relationships and things. In contrast, values of RDF* properties can be both literal values (RDF literals) or nodes connected to other nodes in the graph."
  -   **Capacity to represent edge attributes as nodes**. As we mentioned above, unlike attributes in LPGs, RDF\* edge attributes can be represented as nodes in the graph, allowing them to be treated as individual entities.
  -   **Better expressivity**. RDF\* allows every LPG to be efficiently converted into an RDF model. On the other hand, LPGs cannot fully represent RDF\* because of the rich expressivity of the latter. 
  -   **Arbitrarily complex edge descriptions**. With RDF\*, graph developers can attach complex descriptions to edges that represent connections to other nodes, literal values (strings), and inter-attribute relationships. In contrast, with LPG, edge properties can only be represented as literal key-value pairs.

## References

- [[ar.postgresql-oracle-graph-query-language-standards-adoption-green]]
- [Graph databases don't provide a significant advantage over well-architected relational DBs for most use cases](https://www.linkedin.com/pulse/graph-relational-enemies-alastair-green/?trackingId=5xrQz85vQRaoTnQv%2BO3bPA%3D%3D)
- https://www.researchgate.net/publication/342956606_Linked_Data_for_Smart_Homes_Comparing_RDF_and_Labeled_Property_Graphs