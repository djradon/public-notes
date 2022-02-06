---
id: aFaPiJ9pBtR8d7KAxZhFA
title: Published Subjects Definitions Requirements and Examples
desc: ''
updated: 1635743455159
created: 1635741884856
---


maybe you just need publishers to say "this is a published subject indicator"

- [[p.hasURL]] https://www.oasis-open.org/committees/tm-pubsubj/docs/recommendations/general.htm
- [[p.hasEditor]] @Bernard-Vatant
- [[p.hasTheme]] [[t.cs.web.topic-maps]]
- [[p.hasHighlight]]
  - "Subjects": "can be anything deserving to be identified, named, represented and generally talked about - otherwise said a subject of conversation"
  - "topic": " the representation, inside an application, of an unique, well-defined, and non-ambiguous subject"
  - "Published Subject Identifier" is a URI that resolves to a "human-interperable" "Published Subject Indicator": basically just provide an enumeration of "published subjects" which is an improvement because "publisher's statement of purpose, disambiguation of the subject, and stability. 
  - Recommendations:

> Recommendation 1 :
>
    A Published Subject Indicator should provide human-readable metadata.
> 
> Recommendation 2 :
>
>    A Published Subject Indicator should provide machine-processable metadata.
>
> Machine-processable metadata is recommended so that applications can use more information on the subject than solely URI identification.
>
>Human-readable as well as machine-processable metadata can be included in the Subject Indicator itself (e.g. RDF metadata), or in a separate resource referenced from the Subject Indicator (e.g. XTM metadata).
>Deliverable 2 will provide complementary recommendations on the nature of those metadata.
>
>Recommendation 3 :
>
>    Metadata defined in 1 and 2 should be consistent, but not necessary equivalent.
>
>Consistency between human-readable and machine-processable metadata is the warrant of consistent "interpretation" by applications and humans. This can be achieved, for example, by human-readable metadata being an expression of machine-processable metadata. This issue will be addressed by Deliverable 2.
>
>Recommendation 4 :
>
>    Published Subject Indicator should indicate that it is intended to be a PSI.
>
>This statement of purpose has to be clearly endorsed by the publisher (see below).
>
>Recommendation 5 :
>
>    Published Subject Indicator should identify its publisher.
>
> Publisher is to be understood here in its Dublin Core definition: "An entity responsible for making the resource available."
> 
>Statement of purpose and Publisher identification are the warrants of trust, fundamental to efficient PSI mechanism.
