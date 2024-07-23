---
id: nmgqmbzh6ftaa7jj2woieqa
title: Some Open Issues after Twenty Years of Formal Ontology
desc: ''
updated: 1721759468186
created: 1721684494111
---

- file:///C:/Users/drichardson/Downloads/FAIA306-0001.pdf
- authors: [[user.stefano-borgo]] @pascal-hitzler

## Highlights

- "If we use a decidable logical language, for technical reasons the capacity of the language to express the needed information is limited and the logical theory will not be able to include basic information (for instance, these languages have limitations in coding ternary relations like “z is between x and y” or “x counts as y at time t”)."
  - t.2024.07.22.14 Really?!? @chatgpt thinks you can use a relator without losing decidability
- Another issue regards the proposal presented in [9] to separate ontologies in four types: top-level, domain, task and application ontologies.

### Distinction between types of ontologies

- As proposed in [[ar.formal-ontologies-and-information-systems]]
  - Top-level ontologies are devoted to “describe very general concepts like space, time, matter, object, event, action, etc., which are independent of a particular problem or domain”; domain ontolo- gies “describe [...] the vocabulary related to a generic domain (like medicine, or automo- biles)”; task ontologies “a generic task or activity (like diagnosing or selling)”; finally application ontologies “describe concepts depending both on a particular domain and task, which are often specializations of both the related ontologies. These concepts often correspond to roles played by domain entities while performing a certain activity, like replaceable unit or spare component.
    -  today domain ontologies and application ontologies are largely used as synonyms, task ontologies are rarely addressed and the most recognized (and perhaps useful) separation is between top-level ontologies and application ontologies
    -  the practitioner often finds it hard to distinguish the classification of entities by type and by role.
    -  the ontology is naturally influenced by the observer’s perspective and this freezes the entities into their contextual roles. Once an entity is seen as main- taining the same role across any scenario in the application at stake, the importance of the theoretical distinction between the entity and its role fades away.

### foundational ontology and philosophy

- while a top-level ontology is a classification system that deals with general domain-independent categories only, a [[t.km.ontology.foundational]] is a top-level (formal) ontology that has been built and motivated by the upfront and explicit choice of its core principles. 
  - principles are about fundamental choices: the understanding of space/time, the relationship between entities and space/time, the existence of objects and/or events, the existence of abstract entities, of possibilia, of types of properties, the relationship between objects/events and their properties, the identity conditions, the dependence relationships and so on
- Some of the existing formal ontologies go further and explicitly adhere to specific philosophical schools. 
  - [[prdct.basic-formal-ontology]] is an attempt to translate an interpretation of scientific realism into logical form,
  - [[prdct.gfo]] relies in a form of conceptual realism called [[t.phil.realism.integrative]]
  - We note that today no philosophical school recognizes these systems as truly representative of (a form of) realism
  - unclear whether these philosophical stands have a technical impact. 
- conceptualist approach: [[prdct.unified-foundational-ontology]]
- [[prdct.dolce]] requires only ontological coherence and lets users maintain their world
view by showing how to integrate different modeling perspectives within a single formal
ontology
- [[prdct.sumo]] was developed by assembling off-the-shelf formal theories
that together could cover the most general categories. 
  - [[prdct.iso-15926]] is 4D

### do philosophical distinction matter?

- Given this brief outlook of some formal ontologies, one wonders whether their different stands have a real impact in the use of the formalized systems. Here things are less clear. Generally speaking, where something cannot be modeled directly because of an ontological distinction (e.g. the sharp distinction between material and information objects blocks the simple representation of common-sense objects like a book), these ontologies propose reformulation patterns that are often successful (e.g. the distinction of the book as the material entity and the book as the information entity among which a representation relation holds). Yet, this method cannot always work due to the idiosyncrasy of some application domains and the complexity of some concepts used in applications. To state it briefly, all these ontologies explicitly state their core principles but then allow the user to add arbitrary categories even though these are not ontologically justified or justifiable. While this is built-in in ontologies like DOLCE and GUM, unprincipled ex- tensions should be alien to formal ontologies that adhere to some philosophical school. For the latter systems, the actual exploitations of the ontology in application domains are philosophically wrong but practically accepted, and since an applied ontology has its raison d’être in its use, they make a virtue out of necessity.
- [[prdct.dol-distributed-ontology-model-and-specification-language]]

### Conclusion

#### formal vs. ad-hoc

- highly formal ontology modeling leads more likely
to robust ontologies, which by construction are reusable in many contexts, their genera- tion also requires significant efforts. 
- ad-hoc computational ontologies are rather cheap to produce, but tend not to follow quality principles and are extremely limited in terms of reusability, which in turn means that it often seems to be easier to make a new ontology rather than attempt to reuse or modify such an ad-hoc ontology. 
  - One important reason is that ad-hoc ontologies tend to be developed taking a particular viewpoint or purpose, and this makes it hard to adapt them to different contexts or uses. 
  - Consequently, ad-hoc ontologies have a significant cost factor in terms of time and expertise required when they are to be updated, modified, or repurposed. 
- We still do not have an active line of research on how to achieve such a favorable trade-off, nor even a list of quality metrics to evaluate such result.

#### comprehensive vs shallow axiomatization

- relates to both:
  - choice of logical knowledge representation language used for the encoding (which sometimes is driven by application constraints),
    - both description logics and rules have been posited as favorable for several reasons [28], however hardly any research has been done on this question.
  - how deeply axiomatized
    - Few axioms thus lead to ambiguities, while many axioms put hard constraints on reusability

