---
id: zo9radyrcqngb8cooi6x6n5
title: Event
desc: ''
updated: 1717195013623
created: 1717106200707
---

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
-  making a clear distinction between named places and spatial regions enables one to deal properly with the phenomenon of places changing their absolute spatial location over time.

## References

- [[ar.advanced-ontology-topics-events-roles-artifacts]]
- [[ar.lode-linking-open-descriptions-of-events]]