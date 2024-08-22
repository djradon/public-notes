---
id: gpjt0tgwkb6khor1tcvlgmb
title: Work, Expression, Manifestation, Item
desc: 'WEMI '
updated: 1724344828141
created: 1701423935574
---

- implementations: [[prdct.frbr-core]] [[prdct.fabio]] [[prdct.functional-requirements-for-information-resources-frir]] [[prdct.anglo-american-cataloguing-rules-aacr2]] [[prdct.resource-description-and-access-rda]]

![](/assets/images/2024-08-22-09-39-54.png)

## Terms

### Endeavor

- a super-class created by [[prdct.openwemi]] to encompass all the layers/planes
- might better be called a "creation", as endeavor (imho) could include trying to shower more often

### Superwork

- "works and their instantiations cluster in metaphorical constellations, having orbital and therefore gravitational relationship to each other, and that there are different sorts of celestial bodies in the bibliographical universe. These “constellations” are groupings of instantiations of works — not only the progenitor work itself, but also its editions, translations, abridgments, adaptations, excerpts, etc., and their instantiations as well. These have been termed variously “bibliographic families” (Wilson [1978]), “superworks” (Svenonius 2001), “textual identity networks” (Leazer and Furner 1999), and “instantiation networks” (Smiraglia 2008)." [^2]

### Work

- the essence of a creation, such as a novel, a symphony, a painting, a statue, a thesis
- analagous to Platonic Form
- have two properties:
  - ideational content
    - changes are called mutations
  - semantic content
    - changes are called derivations
- The main purpose of this class is to enable bringing together intellectually equivalent Expressions in order to display to a user all available alternatives of the same intellectual or artistic content.
- A Work is the outcome of an intellectual process of one or more persons. 
- Inherent to the notion of work is the existence of recognisable realizations of the work in the form of one or more expressions. 
  - Works are often regarded as finished and discrete e.g. when declared as such by the creator of the work or based on the elaboration or logical coherence of its content. 
  - However, works may be recognized as existing but unfinished e.g. if the creators deliberately or accidentally never explicitly finished a particular Expression but have left behind partial expressions.
  - In the absence of explicit information about the initial conception, which is rarely available, the first expression created constitutes witness of the beginning of existence of a Work.

### Expression

- realisations of Works in the form of identifiable immaterial objects, such as texts, poems, jokes, musical or choreographic notations, movement pattern, sound pattern, images, multimedia objects, or any combination of such forms. 
- The substance of F2 Expression is signs
- Expressions do not depend on a specific physical carrier and can exist on one or more carriers simultaneously. 
  - As far as bibliographic practice is concerned, only instances of F2 Expression that are externalised on physical carriers other than both the creator's brain and an auditor's brain are taken into account.
- Differences in form imply different Expressions (e.g., from text to spoken word, a transcript of a recording)
- Similarly, differences in language or means of performance imply different Expressions
- if a text is revised or modified, the result is considered to be a new F2 Expression
- While theoretically any change in signs will result in a new Expression, conventionally the context and use will determine the rules for distinguishing among expressions.
- "There are many ways a work can be expressed, and it can be difficult to determine what constitutes a separate expression, and what is a new work entirely; cataloger judgment is required. In general, translations, revisions, versions, illustrated editions, abridgements, and illustrated editions would be considered unique expressions of the same work." [^1]
- In D&D, each edition has its own expression of spells, items, classes, etc.
- In-world, each setting? has its own version of these thing? Or each ruleset.
- "Most works will have only one or two expressions—a text version and a spoken word version, say—but a great classic like Pride and Prejudice is likely to have many expressions."

### Manifestation

- comprises products rendering one or more Expressions
- A Manifestation is defined by both the overall content and the form of its presentation. 
- The substance of F3 Manifestation is not only signs, but also the manner in which they are presented to be consumed by users, including the kind of media adopted.
- An F3 Manifestation is the outcome of a publication process where one or more F2 Expressions are prepared for public dissemination, but it may also be a unique form created directly on some material carrier without the intent of being formally published.
- Manifestation can be identified by the physical features for the medium of distribution, if applicable.
- In the case of industrial products such as printed books or music CDs, but also digital material, an instance of F3 Manifestation can be regarded as the prototype for all copies of it.
- An instance of F5 Item that consists of a physical object or set of objects with clear physical boundaries is also an instance of E22 Human-Made Object. An instance of F5 Item that is stored on a part of a larger physical support (such as an electronic file among others on a disc) can also be considered to be an instance of E25 Human-Made Feature.
- The notion of F5 Item is only relevant with regard to the production process, from a bibliographic point of view. The physical units managed by cultural heritage institutions in their holdings are a distinct notion: a unit of holdings certainly can be equal to an instance of F5 Item, but it also can be either 'biggerâ€ than one (e.g., when two instances of F5 Item are bound together (in the case of printed books)), or 'smaller' than one (e.g., for incomplete holdings, such as when only one CD from a two-CD set is held).
- "A single expression may have many manifestations, especially if (as with Pride and Prejudice) the book is frequently reprinted."
- In D&D, could a manifestation be [[prdct.roll20]]'s version of a thing vs [[prdct.one_dnd]]? That's oow
  - t.2024.08.21.11 
    - yes, as long as all the (observable) symbols are the same?
    - no, since the underlying representation are probably different?
    - might depend on what "thing" is. But if it's a spell, as opposed to a spell-casting interface, I'm leaning to yes
  - t.2024.08.21.12
    - ~[[ar.functional-requirements-for-information-resource-provenance-on-the-web#^w1t3fxtaiozl]]
- in-world, 
  - in a place without mass-production, unique items have a single manifestation. But perhaps in a bespoke workshop, a certain well-honed process could lead to a manifestation of an object with multiple corresponding items? 
  - or maybe groups of things that don't have distinct identities 

### Item

## Issues

- 'Despite initial positive assessments of FRBR clarifying the thoughts around the conceptual underpinnings of works, there has been later disagreement about what the Group 1 entities actually mean.[[5]](https://en.wikipedia.org/wiki/Functional_Requirements_for_Bibliographic_Records#cite_note-5) The distinction between Works and Expressions is also unclear in many cases.'
- [[Resources That Refer Vs Resources That Are|vs.resources-that-refer-vs-resources-that-are]]
- [[idea.instances-are-sometimes-classes]]
- a group of concrete things: set of items? or manifestation
  - t.2024.08.21.12 set of items
- the relationships between the WEMI entities are disjoint from each other and are fixed in order. Being disjoint, the entities cannot share data elements if RDF reasoning will be applied. 
  - This is mainly a problem with sharing between metadata schemas that have distributed their data elements differently, such as the BIBFRAME three-level model and the Resource Description and Access (RDA) adherence to the four-level models of FRBR or LRM.(Baker, 2014) 
  - In the FRBR model all intervening entities are required: the only route from the manifestation to the work is through the link between manifestation and expression and between expression and work. (Shotton, 2019) The relationships are therefore immutable and all “higher” entities must be present for a “lower” entity to be described.


## References

[^1]: https://rdabasics.com/2012/08/24/theoretical-foundations/
[^2]: [[ar.isko.work]]

- https://cidoc-crm.org/extensions/lrmoo/owl/1.0/LRMoo_v1.0.owl
