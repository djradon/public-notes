---
id: 178ZuAuS3pVbx4PGWgAWj
title: Semantic Web
desc: 'the vision: distributed, interoperable, and well-defined data'
updated: 1727283479872
created: 1633629215451
---

- [[p.isRelated]]
  - [[t.cs.web.w3c.rdf.iri]]
  - https://en.wikipedia.org/wiki/Semantic_publishing 
    - "Semantic publication provides a way for computers to understand the structure and even the meaning of the published information, making information search and data integration more efficient" 
  - [[prdct.linked-data-fragments]]
  - [[idea.the-semantic-web-is-dead]]

## Philosophy

### Original Vision

- @tim-berners-lee: "I have a dream for the Web [in which computers] become capable of analyzing all the data on the Web – the content, links, and transactions between people and computers. A "Semantic Web", which makes this possible, has yet to emerge, but when it does, the day-to-day mechanisms of trade, bureaucracy and our daily lives will be handled by machines talking to machines. The "intelligent agents" people have touted for ages will finally materialize."

### Why do we need the semantic web?

- @gavin-mendel-gleason: "Because distributed, interoperable, well-defined data is literally the most central problem for the current and near-future human economy. Knowledge is power, and distributable, actionable knowledge, creates opportunities and efficiencies impossible without it."

## Interesting

### CURIEs

- a CURIE (Compact URI) is a compact representation of a Uniform Resource Identifier (URI). CURIEs are designed to shorten the lengthy URIs often used in Semantic Web technologies, making them more manageable and easier to read. The structure of a CURIE is generally divided into two parts: a prefix and a reference. 
  - e.g.: `foaf:Person`

## Solutions

- [[prdct.swrl]]

### Reasoners

- [[prdct.eye]]

## Issues



### n-ary relationships

- according to [^1], no problem! ^hpcz3e0llqgb
- according to https://terminusdb.com/blog/graph-fundamentals-part-3-graph-schema-languages/ lots of problems
  - no closed-world
  - different meaning for domain and range in rdfs vs owl
- according to https://www.datasciencecentral.com/why-graphql-will-rewrite-the-semantic-web/
  - too complex
  - lack of intrinsic sequencing


### sameAs vs exactMatch 

- Use owl:sameAs when you are certain that two URIs refer to the same entity in every possible way.
- Use skos:exactMatch when you want to link concepts that are highly similar or equivalent, especially in the context of knowledge organization and concept mapping, but where there may be some contextual or definitional differences.

### Complexity

- according to [[ar.topquadrant.why-i-dont-use-owl-anymore]], "I no longer used RDFS/OWL. I now use [[prdct.shacl]] for everything... because I like to keep things as simple as posssible".

## Resources

- https://www.w3.org/wiki/RdfThesaurus
- [[book.design-and-implementation-of-ontologies-in-java-and-apache-jena]]
- [^1]: https://www.w3.org/TR/swbp-n-aryRelations/
- [[book.foundations-of-semantic-web-technologies]]
- https://github.com/semantalytics/awesome-semantic-web

## References

- [[ar.a-review-of-the-semantic-web-field]]
- 