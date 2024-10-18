---
id: ZvBXkgWq3edRQ7TAYBG7a
title: Property Graphs Vs Semantic Graphs
desc: ''
updated: 1729282614757
created: 1633596039729
---

- [[p.hasComparand]]
  - [[t.cs.graph.semantic-graph]]
  - [[Property Graph|t.cs.graph.property-graph]]


## thoughts

- they can be mapped to each other [^2]
- property graphs support key-value pairs on entities and relationships
  - "Naturally annotated edges instead of inconvenient reification in knowledge graphs." [^1]
  - but values are not other nodes
- [when semantic graphs support reification, aren't they essentially the same?][1]
  - maybe, and I think predicates are adequate to represent key-value pairs on
    - subjects/objects (aka "things" or, in graph theory, [[gd.concepts.nodes]])
- for time travel, maybe could be nice to have properties for valid datetimes

## [[p.isRelated]]

- [1]: [[ar.forbes.when-graphs-collide-the-coming-merger-of-property-and-semantic-graphs]]
- [ ] http://blog.liu.se/olafhartig/2019/01/10/position-statement-rdf-star-and-sparql-star/
- https://tdan.com/knowledge-graphs-vs-property-graphs-part-1/27140


## Resources
- https://dzone.com/articles/rdf-triple-stores-vs-labeled-property-graphs-whats
  - "RDF Can Have Multivalued Properties and the Labeled Property Graph Can Have Arrays"
- https://www.wisecube.ai/blog/knowledge-graphs-rdf-or-property-graphs-which-one-should-you-pick/\
  
## References

[^1]: https://docs.arcadedb.com/#Graph-Database
 [^2]: https://protegeproject.github.io/owl2lpg/

- https://flur.ee/fluree-blog/rdf-versus-lpg/