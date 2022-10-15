---
id: eT8Ng8ooUPLhRg3qcLOGK
title: SAM
desc: ' a markup language for semantic authoring'
updated: 1652768347117
created: 1637436632756
---



- [[p.hasSite]] https://mbakeranalecta.github.io/sam
- [[p.wasInspirationFor]] [[gd]]


## [[p.hasFeature]]

- phrases
  -  a piece of text within a paragraph that you want to apply metadata to. A phrase is marked up with curly braces. In the recipe example, the words "Cobb Salad" are marked up as a phrase: {Cobb Salad}. We mark up phrases so that we can add metadata to them with annotations and citations.
- fields
  - a label and a value, e.g. "sugar: 6g"
- annotations
  - links are a type of annotation
  - seems to support "link types"
  - a way of adding descriptive labels or metadata to individual phrases within a text. 
    - metadata types
      - formatting
      - linking
      - semantic 
  - consists of type attribute and optional "specifically" and "namespace" attributes
    - e.g. `{The Duke}(actor "John Wayne" (SAG)) plays an ex-Union Colonel out for revenge.`  
  - can be chained
- citations
  - two forms:
    - internal names/ids
    - citations of external resources
  - for referring to other resources
  - the treatment of the citation is based on the type of object that the citation references, not the type of the citation 
- record sets 

## [[p.hasCon]]

- not designed to be directly human-readable
