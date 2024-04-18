---
id: c8fGFc04CU0O6zEOgg8OT
title: Resources That Refer Vs Resources That Are
desc: ''
updated: 1713467577230
created: 1633593028328
---

- aka: 
  - indicator vs resource
  - sense vs content
  - httpRange-14

## Possibilities

There are four possibilities for a given URI:

- the URI is being used to locate some content
- the URI is being used to refer to a sense
- the URI is being used to identify either content or sense but it’s not specified which
- the URI is being used to both locate content and refer to a sense (ie a property applies equally to both)

## Thoughts

- you could make sure "sense" URIs are just never resources/documents/content,
  - maybe a LOD site has an indicator subdomain and a resource domain, indicator.stagecraft.io and content.stagecraft.io; or probably better, stagecraft.io/i/... and stagecraft.io/content

## Discussion



- "surely the distinction between a network-retrievable information resource and "everything else" is of fundamental importance to the whole architecture of the Web"
- "**Distinguishing between Representations and Descriptions** using URIs, it is possible to identify both a thing (which may exist outside of the Web) and a Web document describing the thing... According to W3C guidelines ([AWWW], section 2.2.), we have a Web document (there called information resource) if all its essential characteristics can be conveyed in a message. Examples are a Web page, an image or a product catalog... The first solution is to use “hash URIs” for non-document resources... a URI that includes a hash cannot be retrieved directly, and therefore does not necessarily identify a Web document... The second solution is to use a special HTTP status code, 303 See Other, to give an indication that the requested resource is not a regular Web document."
  - [[ar.w3.cool-uris]] "https://www.w3.org/TR/cooluris/"
- "the problem surfaces when IRIs are used to identify both a representation, i.e., the bytes on the wire, and an abstract resource such as a person." 
  - "commonly known as the httpRange-14 issue [81], the identifier assigned by the W3C’s Technical Architecture Group (TAG) in its issue tracker. The resolution of that issue was an advice to the community [82] to either use fragment identifiers or HTTP 303 See Other redirects to signal that an IRI identifies an abstract resource (formally known as a non-information resource), such as a person, instead of the returned representation, i.e., the document describing the person."
  - "The most promising proposals at the time of this writing involve “punning” to use the same IRI to mean different things. They use the context in which an IRI is used to determine whether the representation or the abstract concept is meant."
  - 

## Possible Solutions

- the syntactic structure of the URI itself can indicate whether the URI is a subject address or a subject identifier; or else the syntactic context in which the URI is used can determine its role

### 303 redirects

- "use a 303 See Other redirection to a URI whose content (which is the only sense of the URI in this design, remember) describes the original URI"

### Hash URI

This gives a very similar pattern to the 303 redirect, as you can see from the diagram below; the only difference is that instead of following a 303 See Other redirection to get from one URI to the other, you can use URI parsing: you chop off the fragment part of the URI and perform a GET on the resulting URI to get a description.

### Property determines content vs sense

- "The property itself determines whether it applies to the content located by the URI (the page) or a sense referred to by the URI (in this case, the thing the page describes)"
  - "Some properties have a defined domain or range that precludes the property from being used to annotate content." but others don't, e.g. cc:license has a domain of cc:work
- "To support “punning”, therefore, RDF vocabulary designers would need to have additional properties that could be applied to RDF Properties to indicate how their subject (and object where applicable) should be interpreted."

#### Ideas from Topic Maps
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


## References

- [[ar.third-generation-web-apis-bridging-the-gap-between-rest-and-linked-data]]
- http://www.jenitennison.com/2012/05/11/using-punning-to-answer-httprange-14.html