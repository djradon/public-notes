---
id: 6nwlsa50uotwgilu6ba41yb
title: Abc Ontology
desc: ''
updated: 1717176854985
created: 1717175482307
---

- https://dcpapers.dublincore.org/article/952106556

## Model

- entity
  - temporality
  - actuality
  - abstraction

### Temporality

- the ABC model makes it possible to unambiguously express states in which object properties exist, the transitions that demark those states, and the actions and agency that participate in those transitions.
- A state provides the context for framing time- dependent properties of entities. Every ABC description has an implicit global context and can have additional states that are local contexts. Effectively, entities and their property sets that are not associated with a state (through an instate property) exist across time in the world view of the description.
- An event marks a transition from one state to another. Events always have time properties. The effect is that a state implicitly has time duration as defined by its bounding events
  - e.g.: the model could express the loan of the Mona Lisa to the Metropolitan Museum as follows: a instance of the Mona Lisa with a property “located at the Metropolitan” could be associated with a state that is that associated via hasInput and hasOut properties with two events, one of which gives the time of the loan, the other the time of the return
- An action denotes a verb in the context of event– the hasAction property connects an action to an event. Actions provide the locus for Agents and express the responsibility of a person or organization in some act.

### Actuality

- encompasses entities that are sensible – they can be heard, seen, smelled, or touched. 
- entities that are Actualities, can have a time-independent facet and many time-dependent facets. ABC expresses this notion through the inState and hasInstance properties.
  - e.g.: Bill Clinton might have one entity (resource) with the property “born in Arkansas” that is related via the hasInstance property to an entity (resource) with property “President of the United States”
    - The latter would be related via the inState property to a State that resulted from an Event representing Clinton’s election in 1992.
    - The result is a statement that expresses the “sameness” of the two entities (they are both “Bill Clinton”), but the fact that one is an occurrent facet and one is a continuant facet.
- ABC model also incorporates intellectual creation semantics influenced by the [[prdct.ifla-functional-requirements-for-bibliographic-records]]
  - subcategory of actuality is Artifact, expresses sensible entities that are tangible realizations of preconceived concepts, and that can be manifested in multiple ways; e.g., as Manifestations and Items ([[t.library-science.work_expression_manifestation_item]])

### Abstraction

- concepts or ideas
  - never stateful
  - While it can be argued that an idea is “born” at some time, ABC treats the “birth of an idea” when it is manifested in some sensible way; e.g., when it is told, demonstrated, or shown in some manner.
  - ideas cannot exist in isolation in the model. They must be bound to some Actuality through the hasRealization property.
    - t.2024.05.31.10 since psychological modeling is important for [[sh.compnts.cognitive-engine]]

## Foundations

- [[t.phil.time.situational-calculus]]