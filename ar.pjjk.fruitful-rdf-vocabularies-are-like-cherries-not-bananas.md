---
id: ysdbwdb9i0raz8gzqro63ec
title: Fruitful Rdf Vocabularies Are like Cherries Not Bananas
desc: if you want your terms to be widely reused please create them as such
updated: 1701419651596
created: 1701419454590
url: >-
  https://blogs.pjjk.net/phil/fruitful-rdf-vocabularies-are-like-cherries-not-bananas/
---

## Highlights

- "“don’t cherry-pick”, that is: when you borrow or reuse a term from a vocabulary you must comply with everything that the–let’s use the O word here–ontology in which it was defined says about it. That’s not just the textual definition of the term but all that is entailed by statements about domain, range, relationships with other properties and so on. If the original ontology defines, directly or indirectly, “familyName” as being the name of a real person, then don’t use it for fictional characters."
- "Define terms in such a way that they are free from too much baggage: you can always add that later, if you need it, but others can be left to add their own. One example of this is the way in which many Dublin Core Terms are defined without a rdfs:domain declaration."
- "The approach taken by schema.org in some ways goes further by not using rdfs:domain and rdfs:range but instead defining domainIncludes and rangeIncludes where the value is “a class that constitutes (one of) the expected type(s)” (my emphasis): by being non-exclusive domainIncludes and rangeIncludes provide a hint at what is expected without saying that you cannot use anything else."