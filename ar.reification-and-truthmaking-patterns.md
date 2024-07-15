---
id: 31n6gtegjp893vfuiz340ml
title: Reification and Truthmaking Patterns
desc: 'use truthmaking patterns to put truthmakers in the domain'
updated: 1721004300826
created: 1720999931301
---

- http://www.inf.ufes.br/~gguizzardi/ER2018-Truthmaking.pdf
- keywords: [[t.cs.sd.modeling.ontology-driven-conceptual-modeling]]

## Abstract

- Reification is a standard technique in conceptual modeling, which consists of including in the domain of discourse entities that may otherwise be hidden or implicit. However, deciding what should be reified is not always easy. Recent work on formal ontology offers us a simple answer: put in the domain of discourse those entities that are responsible for the (alleged) truth of our propositions. These are called truthmakers. Re-visiting previous work, we propose in this paper a systematic analysis of truthmaking patterns for properties and relations based on the ontological nature of their truthmakers. Truthmaking patterns will be presented as generalization of reification patterns, accounting for the fact that, in some cases, we do not reify a property or a relationship directly, but we rather reify its truthmakers.

## Highlights

### Search for TMs

-  our cognitive domain is much bigger than our domain of discourse
   - e.g., when we say that John and Mary are married, our language only refers to them, although we know that there has been a wedding event and that there is an ongoing marriage relationship. It is up to us to introduce these further entities in our domain of discourse, should we need to represent and reason about them. 
   - Such process of making hidden entities explicit is called reification. ^r9mf84mrcvyu
     - Note that the new entities do not originate from a generic decision to expand the domain, but rather from a transformation of a language construct (typically, a predicate) into a domain element (a “first class citizen”).
 - the basic questions we need to ask to analyze a proposition P are similar to the famous Wh-questions: What is responsible for making P true? When and Where will P be true? 

### Properties and Their Truthmakers

-  only propositions have TMs (they are the only truthbearers) but we shall talk interchangeably of TMs of properties or relations (holding for certain entities), and TMs of propositions
-  take e.g. "a is a rose" vs "a is red"
   -  Strong TM: "existence" (non-descriptive) and "a particular occurrence of redness, that is, a particular event (intended in the most general sense that includes states)" (descriptive)
- non-descriptive properties account for
what something is, on the basis of its nature and structure; descriptive properties
account for how something is, on the basis of its qualities.
- Weak TM makes a proposition true not just because of its existence (i.e., because of its essential nature), but because of the way it contingently is (i.e., because of its actual nature).
  - e.g. Suppose that a is red at time t1, and becomes brown at time t2. 
    - According to the mainstream TM theory, the strong TM of a is brown at t2 will be very different from that of a is red at t1 (i.e., 2 strong TMs)
    - Parsons: the weak TM at both times is the rose itself: since the rose changes while keeping its identity, it is the very same rose, in virtue of the way it (contingently) is at t1 and at t2 (i.e., 1 weak TM)

#### Individual qualities, descriptive properties, intrinsic properties

- This color is modeled as an individual quality in [[prdct.dolce]] and in [[prdct.unified-foundational-ontology]].
- qualities inhere in things, where inherence is a special kind of existential dependence relation, which is irreflexive, asymmetric, anti-transitive and functional
- They are directly comparable, while objects and events can be compared only with respect to a certain quality kind (e.g., to compare physical objects, one resorts to the comparison of their shapes, sizes, weights, and so on
-  Qualities are distinct from their values (a.k.a. qualia), which are abstract entities representing what exactly resembling qualities have in common, and are organized in spaces called quality spaces; each quality kind has its own quality space
   -  e.g. weight is a quality kind, whose qualia form a linear quality space
      -  t.2024.07.14.17 maybe quantitave weight; 
-  quality spaces may have a complex structure with multiple dimensions, each corresponding to a simple quality that inheres in a complex quality.
   -  typical example:  colors and taste
   -  but also mental entities such as attitudes, intentions and beliefs as complex qualities, collapsing, for the sake of simplicity, UFO’s distinction between qualities and modes
-  relational qualities are existentially dependent on the thing they inhere in, but also something else, e.g. John's love for Mary
   -  typical come in bundles called relators
-  summary: individual qualities are weak TMs for descriptive properties