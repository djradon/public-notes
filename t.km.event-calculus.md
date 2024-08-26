---
id: h7obavhdpzwa0bm0xz04gke
title: Event Calculus
desc: 'a logic language for representing actions that have duration and can overlap with each other.'
updated: 1724706655017
created: 1724699985523
---

## Concepts

### Fluent

- a function or a predicate that varies over time, and is used to describe the effects of actions

### Events

- represent changes performed over time
- In the EC, the terms Actions and Events are interchangeable
- Davidson’s theory defines action as a particular subclass of event that is endowed with intentionality.

#### Generalised Event

- a space-time chunk which generalises concepts like actions, locations, times, and physical objects such as things, animals, agents, humans
- @chatgpt.4o: composite events, parameterized events, continuous or ongoing events, abstract events

#### Other Models

- [[prdct.event-ontology]]
- [[prdct.lode-ontology]]
- [[prdct.event-model-f]]
- [[prdct.simple-event-model-ontology]]

- we chose the [[prdct.cidoc-crm]] as reference vocabulary for our ontology for narratives, and we took inspiration in particular from the LODE and SEM ontologies in order to represent the factual components of events

### Conceptualization

#### Narrative

- a story told by and reflecting viewpoint of a narrator (indiv or group)
  - stories have to be consistent with the axioms on physical reality that our ontology is able to capture. 
    - This excludes stories in which, for instance, effects precede causes, events nest circularly, or objects bilocate
- consists of:
  - fabula
  - narrations: correspond to [[pub.question-log.2024.08.26.narratology#bals-definition-of-presentation]]
  - reference: a relation that connects
(fragments of) the narrations to (fragments
of) the fabula, allowing the derivation of the
plot (or syuzhet) of the narrative.


#### Fabula

- significant events of the story
  - t.2024.08.26.13 but "significance" implies narrative viewpoint
  - event: a group of coherent phenomena situated in space and time
    - contextualised in terms of the entities that participate in it.
      - in addition to space and time, the other entities that participate in the event can be identified as having persistent characteristics of structural nature.
- the events in a fabula participate in three main relations
  - **mereological**: connecting events to other events that include them as parts
    - event composition relation is a strict partial order, i.e. it is an irreflexive and transitive relation over the fabula’s events; consequently, it is asymmetric, and more generally acyclic, so that no event is a sub- or super-event of itself or some other event.
  - **temporal occurrence**: associating each event with a time interval during which the event occurs
    - total function
    - each pair of events is connected by one and only one Allen relation
    - Each time interval has exactly one starting time point and one ending time point. 
      - Time points are connected to each other through before, after, or equals relations
    - t.2024.08.26.13 seems potentially naive/overly rigid/digitally over-specified
  - **causal dependecy**: relating pairs of events such that the occurrence of the former causes the occurrence of latter
    - strict partial order
      - acyclicity guarantees that no event is at the same time cause and effect of itself or some other event.
  - In addition to the features of the individual relations in a fabula stated so far, the following conditions are met by every fabula:
    1. The period of occurrence of an event is included in the period of occurrence of any of
    its super-events.
    2. The beginning of occurrence of an event precedes the beginning of occurrence of any event that causally depends on it.

#### Narrations

- a fabula may have any number of narrations, each of which has the obvious characteristic of being about the fabula
  - aboutness is a notion of _representation_
  - "any narration of the fabula must somehow represent the fabula"
    - any proposition in the narration, whether explicitly or implicitly stated, must be true in the fabula.
    - t.2024.08.26.13 again seems naive; narration can represent the narrator's feelings about the fabula
- Each narration has one or more narrators, the authors of the narration, and of a narration content. 
  - the narration content is a message, and it may take any form in which a fabula can be communicated, ranging from text, to audio-visual message, to theatrical enactment, etc
  - we are interested in narrations that have at least one digital representation
    - whether that's the carrier of a non-digital or a born-digital
  - the content will therefore be any media object, i.e. a text, an image, an audio-visual object, or any complex multimedia object that a particular narrator, or group of narrators, choose to tell their version of the fabula

#### Reference

- **reference**: a relation that connects regions of narrations, which we call narrative fragments (or simplify fragments), to events of the fabula
  - Each fragment is maximal, in that it comprises all portions of the narration that narrate the same event.
  - A fragment is identified in ways that depend on the structure of the narration. 
    - For instance, a textual fragment will be a set of disjoint intervals, each giving the boundaries of texts narrating the same event. 
  - A fragment that narrates an event necessarily narrates any of its super-events, and no other event.
- Using the reference relation, it is possible to reconstruct the plot of the narrative, i.e. the sequence of fragments in the order established in the narration by the narrator.
- Because a fabula is identified by its composing events, two narrations of the same fabula may differ for any combination of the following:
  1. the set of events of the fabula narrated by the narrations; each narration may pick a different subset of events, as a way of giving more  emphasis to certain aspects of the story;
  2. the order in which the selected events are narrated;
  3. the expressions used for the narration.

### Representing Narratives in Digital Libraries

- While it is expected that a DL already possesses narrations in digital form, our work is motivated by the target of lifting such narrations into narratives, endowing them with a formal representation of the corresponding fabulae, acting as a semantical counterpart of those narrations
  - t.2024.08.26.13 narration -> narrative means adding fabula and references
- this two-level representation of the narrative allows supporting the union of the use cases supported by the purely syntactical (i.e. based solely on narrations) and the purely semantical (i.e. based solely on fabulae) representations
- A narrative may be constructed in at least two
different ways:
  - **formalisation**: starting from a narration and associating it to a fabula, or
  - **documentation**: starting from a fabula and associating it to a narration of the fabula.
- It must be noted that either the narration or the fabula of a narrative may provide an incomplete, or even inaccurate, account of the story that the narrative is about.
  - t.2024.08.26.13 maybe not surprising, given that fabula means "representation of the fabula" at this point
  - for this reason, the fabula of a narrative must be treated as a knowledge base, i.e., set of statements giving the best available approx- imation of the fabula according to the narrator of the narrative.
- The relationship between the real fabula and its representation may be precisely characterised from a logical point of view as follows:
  - A real fabula _f_ may be seen as a set of possible worlds, namely of the worlds that are compatible with the events in the fabula and the relationships that link these events to each other and to their factual components
  - Let S<sub>f</sub> be the maximal set of formal fabula statements that are true in every world in f
  -  Let k be a non-empty KB with the formal representation of _f_
  -  Then,
     -  k is an accurate representation of f iff every statement in k is true in the fabula, formally iff k |= S f , where |= is the logical implication relation
     -  k is a complete representation of f iff k says everything about f, formally iff S f |= k.
  -  the presence of different versions of the same story is not to be seen as accidental or undesirable in a DL
     - the arising of logical contradictions in a KB is highly undesirable, because it makes the KB unusable
- we view each narrative as a separate KB, and a DL as a set of narratives, possibly sharing a common set of factual components that occur in the fabulae of these narratives

### The NOnt Ontology

- Narrations will be treated as “black boxes”, each represented by a different identifier and characterised as an instance of a special class.
  - Such class will be an extension point of NOnt, in the sense that it is the part of the ontology where the classes and properties for representing narrations can be plugged, for example by drawing them from other standard ontologies.
- Two parts:
  - **NOntNar**: classes, properties and axioms for expressing individual narratives
  - **NOntDL**: classes, properties and axioms for expressing the knowledge in the global KB of a DL

