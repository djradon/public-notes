---
id: c8fGFc04CU0O6zEOgg8OT
title: Resources That Refer Vs Resources That Are
desc: ''
updated: 1635780764399
created: 1633593028328
---



- [[p.alsoKnownAs]] indicator vs subject 

"surely the distinction between a network-retrievable information resource and "everything else" is of fundamental importance to the whole architecture of the Web]"

## Possible Solutions

- the syntactic structure of the URI itself can indicate whether the URI is a subject address or a subject identifier; or else the syntactic context in which the URI is used can determine its role

### Ideas from Topic Maps

- [subject indicators] divided into:
  - 1. resourceRef (subject address)
  - 2. subjectIndicatorRef (subject indicator)

### For GraphDown 

- when regular links (raw URL, URL in angle brackets, or URL in parentheses after single-square link text, aka markdown-style links) for subjects, predicates, and objects, they are always resourceRefs
- wikilinks to notes in the local workspace (LRIs?) or URIs [[https://www.markdownguide.org/basic-syntax/]] are always used as subjectIndicatorRef
  - so you can't say anything about notes themselves?
    - maybe you put it in the frontmatter
    - maybe you create a second, special "ar" note.
    - maybe a special syntax to treat local
      - maybe <http:///vs.rdfs-vs-owl.md>
- if you want to say something about something that's not addressable
  - create a note for it
  - but I wanna use  an "indicator note" that someone else has made? Or I made and published on the web somewhere, and it's not in my local workspace
    - make a new local note, point it at the indicator note. 
- `soln.toml` is kinda an identifier; unlike a corresponding note in the topic hierarchy, it won't change
- differentiate resources that are addressable with `hasURL` - but not sure if that helps

***

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
- 

## what things that refer have in common with things that are
- can have sense of 
  - "Bibliography": other resources related to the thing this note/resource refers to
  - "Footnote": the things that appear in this note can be attributedTo an external resource
- need different predicates for both senses
  - 

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

## [[p.hasRelatedResource]]

- "maybe need to specify whether the note a subject unto itself or an identifier for another subject"
- [ ] [[p.summarized]] [Disambiguating RDF Identifiers](https://www.w3.org/2002/12/rdf-identifiers/) #to-read
- [ ] [[p.summarized]] https://w3c.github.io/rdf-star/UCR/rdf-star-ucr.html#distinguish-interpretation-from-representation
- [1]: [[ar.ontopia.curing-the-webs-identity-crisis]]
- 
