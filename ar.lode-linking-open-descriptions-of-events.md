---
id: wpwzq9ttwck0zgdxivomgiq
title: Lode Linking Open Descriptions of Events
desc: ''
updated: 1717384031921
created: 1717175388199
---

- https://cidoc-crm.org/sites/default/files/14783A.pdf
- comparands: [[prdct.cidoc-crm]] [[prdct.abc-ontology]]

## Event Typology

- One potential problem with building these types of classifications into an ontology for modeling things that happened is that they force a knowledge en- gineer to adopt a particular perspective on what happened.
  - **Distinctions based on aspect or agen- tivity are not necessarily inherent to what happened, but instead are rooted in particular interpretations. **
    - Whether a historical event or a event reported in the news involves an identifiable change or not, or whether agency can be assigned, is often a matter of debate, and its resolution should not be a prerequisite for representing what happened using a concept from an ontology
    - This desire to separate events from their interpretations is what drives the approach taken by DUL, which provides a Situation concept, instances of which may describe different views or interpretations of the same Event instance. 
    - DUL does specialize its Event concept on the basis of agentivity, providing the Action concept for events that have at least one participating agent and the Process concept for events that are not recognized having participating agents.

### Aspect

- whether the event involved is an ongoing activity or process, or the completion of some activity or transition between states.
  - OpenCYC defines a concept called Situation and uses aspect to distinguish between two main specializations of this concept: StaticSituation and Event. The former denotes a situation in which some state of affairs has persisted throughout the situation’s interval of time, while the latter denotes a situation in which some change has occurred during the situation’s interval of time.
  - CIDOC makes a similar but conceptually less clear distinction between two types of E2.Temporal Entity: E3.Condition State and E5.Event. It is less clear because CIDOC also introduces the concept E4.Period, a type of tempo- ral entity that is not static, but does not necessarily involve a change of state. E3.Condition State is also defined narrowly to denote only descriptions of “the prevailing physical condition of any material object or feature” which would seem to exclude descriptions of, for example, the relative state of two things. E3.Condition State is similar to the ABC ontology’s Situation concept, in- stances of which describe the states of tangible things at particular times. The ABC ontology then uses this Situation concept to narrowly define an Event concept as a transition between two different Situation instances. This makes it difficult to describe an event that is characterized by a change in the relationship between two things rather than a change in the state of a single object

### Agent

- OpenCyc and DUL distinguish an Action as a particular type of Event, and CIDOC distinguishes an E7.Activity as a particular type of E5.Event.
- The ABC ontology also distinguishes an Action concept as something performed by an agent, but rather than being a specialization of the Event concept, it is defined as disjoint with the Event concept, which can “contain” actions via a hasAction property.
  - Thus the ABC ontology suggests that events are fully described as sets of actions taken by specific agents, which may be an issue for modeling events such as earthquakes.

## Events and Temporal Intervals

- One approach to linking events to ranges of time uses datatype properties, directly relating event instances with RDF literals representing calendar dates (and thus typed using one of the date-related XML Schema datatypes such as xsd:date or xsd:dateTime). Another approach introduces a class for representing temporal intervals, and uses object properties to link event instances with instances of this class. Temporal interval instances can then be linked to calendar values using datatype properties.
  - ABC, CIDOC, and EO all take the second approach, with ABC and CIDOC introducing classes for temporal intervals, and EO using the TemporalEntity class from OWL-Time 
  - DUL allows both approaches: dates for an event can be directly asserted using the hasEventDate datatype property, or the temporal interval involved can be made explicit by instantiating the TimeInterval class and linking an event instance to it using the isObservableAt object property.
  - The advantage of associating dates directly with events is simplicity: there are fewer abstractions to deal with, and it is simple to filter or sort events using standard date parsing and comparison routines. This also makes it simple to export lists of events for visualization on a timeline. But the tradeoff for this simplicity is an inability to express more complex relationships to time, such as temporal intervals that do not coincide with date units, or uncertainty about when precisely an event took place within some bounded temporal interval. This is a problem for representing historical events ^gg2de01on63i
  - By introducing classes for representing temporal intervals, one can use a temporal calculus for reasoning about these more complex relationships. For example, if the precise date of a historical event is not known but some bound- aries can be established within which it must have occurred, the time between these boundaries can be represented as a temporal interval, and a containment relationship can be asserted between that interval and the (unknown) interval during which the event occurred. The drawback to such an approach is that it can be off-puttingly complex as it introduces a number of abstract entities. The problem also arises of how to either mint URIs to identify these entities or deal with the problems introduced by using blank nodes.

## Events, Spaces and Places

- Events can be linked to abstract temporal regions (Section 2.3) and to abstract spatial regions or to semantically significant places
  - ABC, CIDOC and EO only support linking to spatial regions. 
    - CIDOC provides a class (E53.Place) for “ex- tent in space” to which events can be related via the P7.took place at property. Instances of E53.Place may have names (E44.Place Appellation), but there is no way to link an event to a place name except through a specific spatial ex- tent.
    - ABC’s Place class also emphasizes spatial location rather than meaningful place
    - EO’s place property has a range of wgs84:SpatialThing, which is also defined in terms of spatial extent.
  - Only DUL makes an explicit place/space distinction between Place and SpaceRegion. An event instance can be related to a Place via the hasLocation property, or related to a SpaceRegion via the hasRegion property.
    - scholars may wish to indicate that some event is recorded as having occurred at a mythical place. ^718pmntzkrqp
    - Similar problems are posed by contemporary events which may occur at virtual places such as those found within massive multi-player online environments.
-  making a clear distinction between named places and spatial regions enables one to deal properly with the phenomenon of places changing their absolute spatial location over time. ^a03j97fonuji

## Participation

### Object involvement

- ABC defines two types of properties for relating an Event to a tangible thing (an Actuality in ABC parlance). 
  - The `involves` property does not imply anything beyond simple involvement. 
  - The `hasResult` property relates an Event to a tangible thing or attribute of a thing which exists as a result of that Event.
  - ABC also defines various sub-properties of these two properties that further specialize these meanings. For example destroys is a specialization of involves implying that the involved Actuality ceased to exist as a result of its involvement in the Event.
- CIDOC defines a property P12.occurred in the presence of, which like ABC’s involves relates an E5.Event to a E77.Persistent Item (endurant) without committing to any implied role for that item beyond simple involvement.
  - `P12.occurred in the presence of` is the root of a hierarchy of properties expressing more specialized forms of involvement such as P25.moved and P31.has modified. 
  - Unlike ABC’s Actuality, CIDOC’s `E77.Persistent Item` encompasses not only tangible entities but also intangible concepts or ideas, making CIDOC’s P12.occurred in the presence of a broader concept than ABC’s involves.
- DUL defines a hasParticipant for relating an Event to an Object. Like CIDOC’s E77.Persistent Item, DUL’s Object includes social and mental objects as well as physical ones.
- EO’s factor property, having no range defined, is similarly broad. 
  - EO also defines a `product` property that, like ABC’s `hasResult`, links an Event to some thing that exists as a result of that Event

### Agent participation

- ABC defines a hasPresence property for weakly asserting that an agent was present at an event without implying that the agent took an active role
  - It is specialized by the hasParticipant property, which does imply an active or causal role for the agent
- CIDOC’s equivalent of ABC’s hasPresence is P11.had participant, and its equivalent of ABC’s hasParticipant is P14.carried out by
- DUL’s involvesAgent property is a specialization of hasParticipant for relating an Event to an Agent. EO provides the agent property for the same purpose.
- F stands apart from the other ontologies in what it offers for modeling participation. Using DUL, one can assert that a given object or agent participated in an event. F uses the descriptions and situations (DnS) [^3] pattern to enable a further classification of this participation as an instance of some role-based class
  - e.g.:
    -  using DUL one might state that the agents Brian Boru and M´ael M´orda mac Murchada participated in the Battle of Clontarf
    -  Using [[prdct.event-model-f]], one can further state that the Battle of Contarf is classified as a battle, that battles have commanders, and that Brian and M´ael M´orda are classified as commanders.
-  CIDOC’s P14.1 `in the role of` property provides some support for classifying an agent’s participation in an event as an instantiation of a particular role. However, since it is defined as a property of the P14.carried out by property, it requires the use of OWL Full. 
   -  there does not seem to be a way to associate roles with generic event schemas in the manner described above.
-  


## References

[^3]: [[ar.understanding-the-semantic-web-through-descriptions-and-situations]]