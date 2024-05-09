---
id: r7wmmwwaws15llja6y5ng7h
title: Sumo
desc: 'Suggested Upper Merged Ontology, with Physical (spatiotemporal) and Abstract'
updated: 1715275986724
created: 1708625059084
---

- [[c.ontology.upper]]
- url: https://raw.githubusercontent.com/abrahaj/SUMO.owl/master/SUMO.owl
- similar: [[prdct.milo]]
- related: [[prdct.sigmakee]] 

## Implementations

- [[prdct.grammatical-framework]] see https://publications.lib.chalmers.se/records/fulltext/116606.pdf
  - The representation of SUMO in GF preserves the expressivity of the original ontology, adding to this the advantages of a type system and built-in support for natural language generation.

### Confusing representation with implementation

- It is important not to confuse representation with implementation. Performing representation in the same language as the implementation risks using a language that makes it impossible (or at least very difficult or awkward) to capture certain kinds of information. For example if your implementation language doesn't allow for stating if..then rules, then you won't be able to capture that kind of information. But such rules are almost certainly needed to define each term precisely. A better approach is to capture the information and then decide how, and how much, of that knowledge can be expressed and used efficiently in your application. At least you'll have documented carefully what your concepts mean. Just because implementations can't directly reason with English, doesn't mean we shouldn't have English definitions in our data dictionaries.

## Comparisons

### vs Cyc

- the only product truly comparable to SUMO in terms of size, scope and degree of formal definition is [[prdct.cyc]]

### WordNet

- [[prdct.wordnet]] is lexical

### Dolce

- [[prdct.dolce]] uses classes and properties in the service of describing particulars and has a set of metaproperties that aren't defined in DOLCE itself

### BFO

- [[prdct.basic-formal-ontology]] - limited in scope

### OWL

- "a logical language with a simplistic upper ontology"

## Conceptual Model

![](/assets/images/2024-03-06-21-42-31.png)

![](/assets/images/2024-03-06-21-42-47.png)

![](/assets/images/2024-03-06-21-43-01.png)

## Resources

- [[book.ontology-a-practical-guide]]
- [[ar.semantic-modeling-with-sumo]]
- https://www.ontologyportal.org/FAQ.html