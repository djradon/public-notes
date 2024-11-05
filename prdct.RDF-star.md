---
id: lTim9plsY3OzVv6gn7TBR
title: RDF-star
desc: ''
updated: 1730843232312
created: 1634426288630
---



- [[p.hasURL]] https://w3c.github.io/rdf-star/
- [[p.hasRepository]] https://github.com/w3c/rdf-star/
- aka: RDF-*
- [[c.usecase]] https://w3c.github.io/rdf-star/UCR/rdf-star-ucr.html#submitted-use-cases

## Features

- makes use of the "many-to-many" nature of reifiers, where multiple triples can be reified at once, and several reifiers can be related to the same triple
- 

## To Do

- [ ] [[p.summarized]] rdf-star use cases 
  - https://gist.github.com/niklasl/f4a5dee1b991ff5a19a33360c6fd3078

## Implementations

- [[prdct.ontotext-platform]]

## Issues

- https://w3c.github.io/rdf-star/cg-spec/editors_draft.html#sa-mode-and-pg-mode
  - are quoted triples asserted?
    - t.2023.12.01 depends on the implementation!?
      - [[prdct.JSON-LD.star]] has embedded nodes for non-assertion, annotation objects for assertion
- https://w3c.github.io/rdf-star/cg-spec/editors_draft.html#the-seminal-example
  - can you have multiple identical triples?
    - nope! have to use standard reification, new relationship concept
      - but don't need them anyhow if you're not asserting the triples (ie., Separate Assertion / SA) or if the thing asserted is quoted and assigned a temporal / instance info
    - [[t.phil.type-token-distinction]]
      - https://www.w3.org/2021/12/rdf-star.html#occurrences
- Referential Opacity
  - https://www.w3.org/2021/12/rdf-star.html#ref-opacity
  - https://github.com/w3c/rdf-star/issues/22
  - t.2024.06.07.10 things should be opaque most of the time, since it's important for beliefs and provenance, and since you can get transparency from opacity
    - but see https://github.com/w3c/rdf-star-wg/wiki/RDF%E2%80%90star-examples-of-profiles#9-why-opaque-triples-do-not-work-for-data-integration-p-a-champin for an argument that opaque isn't sufficient, but it's possible that Charlie's sameAs is incorrect 
  - [[email.public-rdf-star.some-notes-on-the-rdf-star-examples-of-profiles]]


## Possible Features

- https://lists.w3.org/Archives/Public/semantic-web/2009Nov/0040.html


## Resources

- https://www.ontotext.com/knowledgehub/fundamentals/what-is-rdf-star/

## References

- [[ar.medium.dallemang.why-im-not-excited-about-rdf-star]]
- https://www.youtube.com/watch?v=gTMvHJdMnzI