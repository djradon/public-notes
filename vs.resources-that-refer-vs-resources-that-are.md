---
id: c8fGFc04CU0O6zEOgg8OT
title: Resources That Refer Vs Resources That Are
desc: ''
updated: 1705691852929
created: 1633593028328
---

-- aka: indicator vs resource


- "surely the distinction between a network-retrievable information resource and "everything else" is of fundamental importance to the whole architecture of the Web"
- "**Distinguishing between Representations and Descriptions** using URIs, it is possible to identify both a thing (which may exist outside of the Web) and a Web document describing the thing... According to W3C guidelines ([AWWW], section 2.2.), we have a Web document (there called information resource) if all its essential characteristics can be conveyed in a message. Examples are a Web page, an image or a product catalog... The first solution is to use “hash URIs” for non-document resources... a URI that includes a hash cannot be retrieved directly, and therefore does not necessarily identify a Web document... The second solution is to use a special HTTP status code, 303 See Other, to give an indication that the requested resource is not a regular Web document."
  - "https://www.w3.org/TR/cooluris/"

## Possible Solutions

- the syntactic structure of the URI itself can indicate whether the URI is a subject address or a subject identifier; or else the syntactic context in which the URI is used can determine its role

### Ideas from Topic Maps

- [subject indicators] divided into:
  - 1. resourceRef (subject address)
  - 2. subjectIndicatorRef (subject indicator)

### For [[semantic_md]] 





## Thoughts

- is it the same as "[interpretation vs representation](https://w3c.github.io/rdf-star/UCR/rdf-star-ucr.html#distinguish-interpretation-from-representation)"
- > RDF has not been clear about whether a URI like "http://www.w3.org/Consortium" identifies the W3C or a web page about the W3C 
- notes/URIs/RRIs that refer to things (people, books, articles) 
  - could be called:
    - reference notes
    - pointer notes
  - could further differentiate notes that refer to topics / abstract things
- notes/URIs/RRIs that are actual things (daily notes, task items, statements, (unpublished) articles, blogs)
    - could be called
      - resource notes

## what things that refer have in common with things that are

- can have sense of 
  - "Bibliography": other resources related to the thing this note/resource refers to
  - "Footnote": the things that appear in this note can be attributedTo an external resource
- need different predicates for both senses


## Notes (in the Dendron sense)

- differentiate between notes that represent something (e.g. topics, solutions) and notes that are something (vs, journal)
  - comes down to "is about" something vs "is (a literary) something"?
    - could come down to resources being terms (instead of topics) [[vs.terms-vs-topics]]
      - and contextual terms at that
    - literary because the only things that refer to something and also are the something they refer to (self-referentiality) are
      - literature
      - symbols
      - computer programs (and some pointers?)
      - maybe logical statement
  - using `type` for both seems wrong 
  - article is interesting b/c it can be both
  - this is different that the class-individual confusion
  - how much does it really matter?
  - I guess resources that are something are just a special case (subset)  of the resources that represent something  ^AQ6h3rFksAfc

## URIs / URLS

- easier to judge from context: is the domain/range of the predicate a IRI? If not, it's about the thing the subject/object IRI refers to

## Resources

- "maybe need to specify whether the note a subject unto itself or an identifier for another subject"
- [ ] [[p.summarized]] [Disambiguating RDF Identifiers](https://www.w3.org/2002/12/rdf-identifiers/) #to-read
- [ ] [[p.summarized]] https://w3c.github.io/rdf-star/UCR/rdf-star-ucr.html#distinguish-interpretation-from-representation
- [1]: [[ar.ontopia.curing-the-webs-identity-crisis]]


I chose not to cover this approach in a lot of detail because it extends the RDF model in a way that no current triple store implements