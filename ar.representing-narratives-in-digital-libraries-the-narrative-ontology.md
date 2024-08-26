---
id: b2cfxfrvhoqezasf2xm2gel
title: Representing Narratives in Digital Libraries the Narrative Ontology
desc: ''
updated: 1724699984654
created: 1724260420812
---

- https://www.semantic-web-journal.net/content/representing-narratives-digital-libraries-narrative-ontology-1
- authors: @carlo-meghini @valentina-bartalesi @daniele-metilli
- related: [[prdct.narrative-ontology-nont]] [[t.lit.narratology]]

## Abstract

- Digital Libraries (DLs), especially in the Cultural Heritage domain, are rich in narratives. Every digital object in a DL tells some kind of story, regardless of the medium, the genre, or the type of the object. However, DLs do not offer services about narratives, for example it is not possible to discover a narrative, to create one, or to compare two narratives. Certainly, DLs offer discovery functionalities over their contents, but these services merely address the objects that carry the narratives (e.g. books, images, audiovisual objects), without regard for the narratives themselves. The present work aims at introducing narratives as first-class citizens in DLs, by providing a formal expression of what a narrative is. In particular, this paper presents a conceptualization of the domain of narratives, and its specification through the Narrative Ontology (NOnt for short), expressed in first-order logic. NOnt has been implemented as an extension of three standard vocabularies, i.e. the CIDOC CRM, FRBRoo, and OWL Time, and using the SWRL rule language to express the axioms. An initial validation of NOnt has been performed in the context of the Mingei European project, in which the ontology has been applied to the representation of knowledge about Craft Heritage.

## Highlights

- formal narratives should not replace traditional, informal narrat- ives: rather, they should enhance them, by adding a formal dimension to the existing one.

### Russian Formalists

- According to the Russian formalists, a narrative consists of:
  – the fabula, i.e., the story itself as it happened, in reality or in fiction;
  – the narrations, i.e., one or more expressions, each in its own language and medium, that narrate the fabula. Each narration corresponds to Bal’s definition of presentation [4];
  – the plot, i.e., the story as it is narrated by the narrator. The plot corresponds to the syuzhet of the Russian formalists and to Aristotle’s logos.
- current digital libraries only contain the "narration" level.

### The Proposal

- "we propose adding a formal expression of the fabula and the plot"
  - knowledge extraction methods from media
objects are central to our proposal - expressed in first-order logic, using [[prdct.swrl]] to express the axioms
- On the basis of the ontology, we have developed the Narrative Building and Visualising (NBVT) tool [6], and applied it in four case studies.  
  - [[prdct.story-map-building-and-visualising-tool-smbvt]]
- includes predicates for representing qualitative temporal knowledge about the intervals of occurrence of events
  - relies on Allen's 13 basic temporal relations (BTRs for short)
    - Allen also provided transitivity rules that allow deriving implicit temporal relations from known ones, which can be expressed in SWRL
    - the temporal relations between two intervals become exponentially many if disjunctions of BTRs are used to state temporal knowledge
      - we were able to find a tractable subset of BTRs
- @seymour-chatman: the elements of a story can be distinguished in: (i) characters, (ii) elements in the scenario.

#### From Event Calculus

- [[t.km.event-calculus]]