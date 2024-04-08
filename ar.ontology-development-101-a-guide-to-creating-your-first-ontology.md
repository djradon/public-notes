---
id: 5x4czy7ll20i5eg8kuynyft
title: Ontology Development 101 a Guide to Creating Your First Ontology
desc: ''
updated: 1712595516107
created: 1712594692678
---

- https://protege.stanford.edu/publications/ontology_development/ontology101.pdf
- topics: [[prdct.protege]]

## Reasons

• To share common understanding of the structure of information among people or
software agents
• To enable reuse of domain knowledge
• To make domain assumptions explicit
• To separate domain knowledge from the operational knowledge
• To analyze domain knowledge

## Highlights

- Subclasses of a class usually (1) have additional properties that the superclass does not have, or (2) restrictions different from those of the superclass, or (3) participate in different relationships than the superclasses
- the ontology should not contain all the possible properties of and distinctions among classes in the hierarchy,
  - e.g. Consider an ontology describing biology experiments. The ontology will likely contain a concept of Biological organisms. It will also contain a concept of an Experimenter performing an experiment (with his name, affiliation, etc.). It is true that an experimenter, as a person, also happens to be a biological organism. However, we probably should not incorporate this distinction in the ontology: for the purposes of this representation an experimenter is not a biological organism and we will probably never conduct experiments on the experimenters themselves. If we were representing everything we can say about the classes in the ontology, an Experimenter would become a subclass of Biological Organism. However, we do not need to include this knowledge for the foreseeable applications. In fact, including this type of additional classification for existing classes actually hurts: now an instance of an Experimenter will have slots for weight, age, species, and other data pertaining to a biological organism, but absolutely irrelevant in the context of describing an experiment. However, we should record such design decision in the documentation for the benefit of the users who will be looking at this ontology and who may not be aware of the application we had in mind.

## inverse slots

- the