---
id: ghlsg7kgdqzmhsebsf4df3m
title: Foundational Ontologies in Action
desc: ''
updated: 1731023989221
created: 1709751228551
---

- authors: @stefano-borgo
- url:
  - https://drive.google.com/open?id=1-M83WYA8yDFSL8I4ZmzSgBRmkZ6O5qOI&usp=drive_fs
  - https://www.academia.edu/80990810/Foundational_ontologies_in_action
- mentions: [[org.international-association-for-ontology-and-its-applications]]
- compares: [[prdct.basic-formal-ontology]] [[prdct.dolce]] [[prdct.gfo]] [[prdct.gum]] [[prdct.tupper]] [[prdct.unified-foundational-ontology]] [[prdct.yamato]]

## Thoughts

- Only a programmer would define Red as a literal #FF0000 - That's why LLMs are so great... they support fuzziness.


## Highlights

- "All ontologies recognise the distinction between terms denoting individuals and terms denoting generic covering entities by which individuals may be counted as in some way the “same” – whether these be classes, containing individuals as members (e.g., the class of all cats), concepts by which we group together individuals sharing a salient set of common properties (e.g., the idea of cats in general), or some hard-to-define notion of categories, kinds, or universals to which particular individuals are related as instances (the generic cat)... This was already a topic of concern in mediaeval philosophy, where it showed up as the debate between Realists, for whom universals were real-world entities, and Nominalists, for whom they were merely labels, or concepts, used to impose an intelligible order on reality but not themselves part of that reality. The debate is alive and kicking in modern ontology too, as witness the debate between realism and conceptualism played out in the recent exchange of articles (Merrill, 2010a; Smith and Ceusters, 2010; Merrill, 2010b)."
- "some ontologies (e.g., DOLCE) include a category of abstracts in their taxonomy, whereas others (e.g., BFO) do not. Ontologies of the former kind treat times and places, for example, as abstract entities, whereas for those of the latter, they are regarded as concrete, times being occurrents and places continuants."
- "Substance vs Accident. In classical logic, an entity’s properties are expressed by means of pred- icates such as “. . . is red”, where the dots represent the fact that, as Frege held, predicates are “unsaturated”. This means that a predicate only expresses a thought when combined with a term denoting an entity that may or may not have the property expressed by the predicate.13 Here prop- erties are not themselves entities and so have no place within an ontology’s taxonomy. But this is not the only possible approach. Instead of seeing “Mars is red”, in Fregean fashion, as the result of applying the predicate “. . . is red” to the name “Mars” (where the latter, but not the former, denotes an individual entity), we could rather see it as the result of applying a relational predicate “. . . is . . . ” to two entity-denoting expressions “Mars” and “red”, so that the thought is of a rela- tion holding between the entities they denote. To complete this picture, though, we must specify what kind of entity “red” denotes, and various possibilities have been explored in the literature. One is that “red” denotes a trope – the individual redness of Mars itself, as distinct from that of, say, the star Antares, even if these are qualitatively identical. Another is to take “red” to denote a universal, the same redness featuring in the thoughts expressed by “Mars is red” and “Antares is red”. A third possibility, used in several ontologies, invokes entities called “qualities”, unique to individuals, such as, for example the colour of Mars and the colour of Antares, and then takes “red” to denote a value that such a quality can assume."

### Constitution / Composition

- an ontology may be compatible with different ‘interpretations’ of the given description, leading to the construction of distinct models, each one compatible and aligned with that ontology

### Roles

- In some approaches, a role is a dependent entity that exists only when played by some other entity (e.g., when roles are taken as ‘realisable entities’, like dispositions, as in BFO). In other views, roles may exist also when no entity is playing them (e.g., when roles are taken as concepts as in DOLCE and YAMATO).
- sometimes an ontology allows one to talk about an entity as player of a role, e.g., a person-as-client in a
business relationship. In the literature, this special kind of entity is known as a qua-entity

### Qualities of objects and events

- A further level of sophistication is to regard the colour of the flower as an entity distinct from either the flower itself or its redness. The colour is an entity specifically dependent on the flower, and at dif- ferent times it may assume different values. Logically, we might crudely characterise this position as HasColour(flower, colour) ∧ HasValue(colour, red, t)
- Traditionally, logical analysis has favoured what might be called a ‘snapshot’ view, according to which there is nothing to change over and above the holding of different static states (‘snapshots’) at different times. Against this, many have argued that changes – represented by, for example, processes or events – should be regarded as some kind of entities in their own right, and indeed most of the ontologies here do indeed include a category of occurrents or perdurants to put them in. Despite this, the analyses offered by the papers collected here are for the most part content to represent the change in colour of the flower in terms of the succession of two states of the world, in one of which the flower is red, and in the other, brown.
- "How is the value of the individual colour of the flower (if reified) related to whatever is denoted by the names such as ‘red’ and ‘brown’ we use to describe them? The different ontologies exhibit a variety of approaches here, the relationship in question depending on what the references of colour names are taken to be. For BFO and GFO, they are universals and the relationship is ‘instance of’; for DOLCE, they are regions and the relationship is ‘part of’; for UFO they are classes and the relationship is ‘member of’; for YAMATO the relationship given is identity."
- "For BFO ‘red’ and ‘brown’ denote subclasses of ‘colour’ whereas for DOLCE they are parts of a colour space and for UFO they are members of a class of colour concepts. GFO states that the universal ‘red’, of which the value of the individual flower colour may be an instance, is part of the “value structure” for measuring and depicting colours, but the nature of this value structure is not further specified. In DOLCE, by contrast, with a colour space corresponding to GFO’s value structure, it is clear that, as in item (3), the parthood relation here is that of subregion"
- YAMATO models the change as a transition between start and end states but it could also represent colour change as an ongoing process. DOLCE even provides a formula to ensure that the change is continuous across the colour space

### Qualities of events

- "YAMATO, takes a very different approach, drawing a sharp distinction between events, which are classical occurrents as just described, and processes, which are more continuant-like in the sense that they can change while unfolding... an event is constituted by one or more processes,"

### Events and Goals

- For BFO a plan is a concretisation of a plan specification whose proper parts include action and objective specifications. The former prescribes a process in which the bearer of the plan (the man) may participate over some interval; this process may or may not achieve the specified objective. In the given scenario the initial plan (walk to the station) is replaced by a new plan (return home) before its objective is achieved.
- In Yamato, "processes are treated as ongoing entities capable of undergoing change as they progress. A plan is understood as a representation of a sequence of actions; it is executed by performing a sequence of actions satisfying it, but may be abandoned if only part of the sequence is performed. In the modelled scenario, a walking process is present over an interval. Over some initial subinterval, this process constitutes an uncompleted execution of the plan to walk to the station. After that the process changes so that during an immediately succeeding subinterval it constitutes a turning event. This is followed by a final subinterval over which the process constitutes a completed execution of a plan to go home."
- In DOLCE a plan is modelled as a concept, which is a non-physical endurant. 
- the UFO analysis uses the walker’s intentions, via the notion of intended destination. A walking event cannot change, so the analysis uses an associated endurant Walk which encapsulates the walker’s intention with his capabilities qua walker. In the given scenario, Walk changes from an ‘ongoing walk’, in which the destination has not yet been reached, to a ‘finalised walk’, in which it has.

### Social concept evolution

- In one case, for instance, the ontology recognises that a term persists in the language but not the meaning it denotes. In another reading, the ontology takes the meaning as persisting even though some regulatory aspects of it may change as time goes on. Another way to tackle the use case is by distinguishing the intensional vs. extensional content of the concept: the intensional content of a concept is the set of properties (including their relationships) that defines the concept, the extensional content is the set of instances of the concept


- Depending on the ontological view, one can decide to read this case in different ways. In one case, forinstance, the ontology recognises that a term persists in the language but not the meaning it denotes. In another reading, the ontology takes the meaning as persisting even though some regulatory aspects of it may change as time goes on. Another way to tackle the use case is by distinguishing the intensional vs. extensional content of the concept: the intensional content of a concept is the set of properties (including their relationships) that defines the concept, the extensional content is the set of instances of the concept.