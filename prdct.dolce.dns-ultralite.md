---
id: ulcpsxyesx6mxgsgapascns
title: DNS Ultralite
desc: 'DOLCE+DnS (Descriptions and Situation) Ultralite ontology'
updated: 1721309008113
created: 1710890567295
---

- [[c.ontology.upper]]
- simplification_of: [[prdct.dolce.lite-plus]]
- related: [[prdct.dolce.d0]] [[prdct.dolce.plans-lite]] [[prdct.dolce.information-objects]] [[prdct.dolce.systems-lite]] [[prdct.dolce.core-legal]] [[prdct.dolce.lexical]]
- url: 
  - http://ontologydesignpatterns.org/wiki/Ontology:DOLCE+DnS_Ultralite
  - http://www.ontologydesignpatterns.org/ont/dul/DUL.owl (v4.1)
  - http://www.ontologydesignpatterns.org/ont/dul/DUL_v40.owl
- authors: [[user.aldo-gangemi]]

## Issues

- properties are all SubProperty of associatedWith

## Description

the DOLCE+D&S Ultralite15 (DUL) OWL ontology was intended to popularize DOLCE to the Semantic Web community. DUL uses DOLCE, D&S, and a few more ontology design patterns (Plan16, Information Object17, and Collection, that extend DOLCE. See [29] for an account of DUL as an architec- ture of ontology design patterns inspired by those integrated theories, and [12] for an integrated axiom- atization of plans, information objects and collections in D&S. DUL is the result of various refinements and integrations of the OWL versions of those theories. The main motivations why DUL was conceived include: (i) intuitive terminology (e.g. substituting Endurant and Perdurant with Object and Event), (ii) lighter axiomatization (e.g. giving up some predicate indexing), (iii) integration of other theories, (iv) semantic-web-oriented OWL2 modeling styles. [^1]

Main aspects in which DOLCE+DnS Ultralite departs from DOLCE Lite-Plus are the following:

- The names of classes and relations have been made more intuitive
- The DnS-related part is closer to the newer 'constructive DnS' ontology (http://www.ontologydesignpatterns.org/ont/cdns/cDnS.owl). 
- Temporal and spatial relations are simplified - Axiomatization makes use of simpler constructs than DOLCE Lite-Plus 
- The architecture of the ontology is pattern-based, which means that DOLCE+DnS Ultralite is also available in modules, called 'content ontology design patterns', which can be applied independently in the design of domain ontologies (cf. http://www.ontologydesignpatterns.org). If many modules are needes in a same ontology project, is anyway useful to use this integrated version. 

### Events

rdfs:comment "Any physical, social, or mental process, event, or state.

More theoretically, events can be classified in different ways, possibly based on 'aspect' (e.g. stative, continuous, accomplishement, achievement, etc.), on 'agentivity' (e.g. intentional, natural, etc.), or on 'typical participants' (e.g. human, physical, abstract, food, etc.).
Here no special direction is taken, and the following explains why: events are related to observable situations, and they can have different views at a same time.
If a position has to be suggested here anyway, the participant-based classification of events seems the most stable and appropriate for many modelling problems.

(1) Alternative aspectual views

Consider a same event 'rock erosion in the Sinni valley': it can be conceptualized as an accomplishment (what has brought a certain state to occur), as an achievement (the state resulting from a previous accomplishment), as a punctual event (if we collapse the time interval of the erosion into a time point), or as a transition (something that has changed from a state to a different one). 
In the erosion case, we could therefore have good motivations to shift from one aspect to another: a) causation focus, b) effectual focus, c) historical condensation, d) transition (causality).

The different views refer to the same event, but are still different: how to live with this seeming paradox? 
A typical solution e.g. in linguistics (cf. Levin's aspectual classes) and in DOLCE Full (cf. WonderWeb D18 axiomatization) is to classify events based on aspectual differences. But this solution would create different identities for a same event, where the difference is only based on the modeller's attitude.
An alternative solution is suggested here, and exploits the notion of (observable) Situation; a Situation is a view, consistent with a Description, which can be observed of a set of entities. It can also be seen as a 'relational context' created by an observer on the basis of a 'frame'. Therefore, a Situation allows to create a context where each particular view can have a proper identity, while the Event preserves its own identity. 
For example, ErosionAsAccomplishment is a Situation where rock erosion is observed as a process leading to a certain achievement: the conditions (roles, parameters) that suggest such view are stated in a Description, which acts as a 'theory of accomplishments'. Similarly, ErosionAsTransition is a Situation where rock erosion is observed as an event that has changed a state to another: the conditions for such interpretation are stated in a different Description, which acts as a 'theory of state transitions'.
Consider that in no case the actual event is changed or enriched in parts by the aspectual view.

(2) Alternative intentionality views

Similarly to aspectual views, several intentionality views can be provided for a same Event. For example, one can investigate if an avalanche has been caused by immediate natural forces, or if there is any hint of an intentional effort to activate those natural forces.
Also in this case, the Event as such has not different identities, while the causal analysis generates situations with different identities, according to what Description is taken for interpreting the Event. 
On the other hand, if the possible actions of an Agent causing the starting of an avalanche are taken as parts of the Event, then this makes its identity change, because we are adding a part to it. 
Therefore, if intentionality is a criterion to classify events or not, this depends on if an ontology designer wants to consider causality as a relevant dimension for events' identity.

(3) Alternative participant views

A slightly different case is when we consider the basic participants to an Event. In this case, the identity of the Event is affected by the participating objects, because it depends on them. 
For example, if snow, mountain slopes, wind, waves, etc. are considered as an avalanche basic participants, or if we also want to add water, human agents, etc., that makes the identity of an avalanche change.
Anyway, this approach to event classification is based on the designer's choices, and more accurately mirrors lexical or commonsense classifications (see. e.g. WordNet 'supersenses' for verb synsets).

Ultimately, this discussion has no end, because realists will keep defending the idea that events in reality are not changed by the way we describe them, while constructivists will keep defending the idea that, whatever 'true reality' is about, it can't be modelled without the theoretical burden of how we observe and describe it. 
Both positions are in principle valid, but, if taken too radically, they focus on issues that are only partly relevant to the aim of computational ontologies, which assist domain experts in representing a certain portion of reality according to their own assumptions and requirements. 

For this reason, in this ontology version of DOLCE, both events and situations are allowed, together with descriptions (the reason for the inclusion of the D&S framewrok in DOLCE), in order to encode the modelling needs, independently from the position (if any) chosen by the model designer."


## References

- [^1]: [[ar.dolce-a-descriptive-ontology-for-linguistic-and-cognitive-engineering]]
- [[ar.understanding-the-semantic-web-through-descriptions-and-situations]]