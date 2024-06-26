---
id: 178ZuAuS3pVbx4PGWgAWj
title: Semantic Web
desc: ''
updated: 1717096671369
created: 1633629215451
---

- [[p.isRelated]]
  - [[t.cs.web.w3c.rdf.iri]]
  - https://en.wikipedia.org/wiki/Semantic_publishing 
    - "Semantic publication provides a way for computers to understand the structure and even the meaning of the published information, making information search and data integration more efficient" 
  - [[prdct.linked-data-fragments]]

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

## Resources

- https://www.w3.org/wiki/RdfThesaurus
- [[book.design-and-implementation-of-ontologies-in-java-and-apache-jena]]
- [^1]: https://www.w3.org/TR/swbp-n-aryRelations/
- [[book.foundations-of-semantic-web-technologies]]
- https://github.com/semantalytics/awesome-semantic-web

## References

- [[ar.a-review-of-the-semantic-web-field]]