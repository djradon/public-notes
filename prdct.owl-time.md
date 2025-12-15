---
id: acxwjynzcfhybxyoe56el4i
title: Owl Time
desc: 'ontology of temporal concepts, providing a vocabulary for expressing facts about topological (ordering) relations among instants and intervals, together with information about durations, and about temporal position including date-time information'
updated: 1765311315474
created: 1701453829509
url: https://www.w3.org/TR/owl-time/
related: 
  - "[[prdct.vocab-owl-time-agg]]"
---

## Highlights

- "A set of ordered intervals (e.g. named dynasties, geological periods, geomagnetic reversals, tree rings) can make a simple form of temporal reference system that supports logical reasoning, known as an ordinal temporal reference system [iso19108]." 
- Four classes in the ontology support an explicit description of temporal position. `[:TemporalPosition](https://www.w3.org/TR/owl-time/#time:nominalPosition#time:TemporalPosition)` is the common super-class, with a property `[:hasTRS](https://www.w3.org/TR/owl-time/#time:nominalPosition#time:hasTRS)` to indicate the temporal reference system in use. `[:TimePosition](https://www.w3.org/TR/owl-time/#time:nominalPosition#time:TimePosition)` has properties to alternatively describe the position using a number (i.e. a temporal coordinate), or a nominal value (e.g. geologic time period, dynastic name, archeological era)
- [[prdct.vocab-owl-time-agg]]'s temporal aggregate seems like it could capture 


### Topological Temporal Relations

- 'The basic structure of the ontology is based on an algebra of binary relations on intervals (e.g., meets, overlaps, during) developed by Allen \[[al-84](https://www.w3.org/TR/owl-time/#topology#bib-al-84 "Towards a general theory of action and time. Artificial Intelligence 23, pp. 123-154.")\], \[[af-97](https://www.w3.org/TR/owl-time/#topology#bib-af-97 "Actions and events in interval temporal logic In: Spatial and Temporal Reasoning. O. Stock, ed., Kluwer, Dordrecht, Netherlands, pp. 205-245.")\] for representing qualitative temporal information, and to address the problem of reasoning about such information.

The ontology starts with a class `[:TemporalEntity](https://www.w3.org/TR/owl-time/#topology#time:TemporalEntity)` with properties `[:hasBeginning](https://www.w3.org/TR/owl-time/#topology#time:hasBeginning)` and `[:hasEnd](https://www.w3.org/TR/owl-time/#topology#time:hasEnd)` that link to the temporal instants that define its limits, and `[:hasTemporalDuration](https://www.w3.org/TR/owl-time/#topology#time:hasTemporalDuration)` to describe its extent. There are two subclasses: `[:Interval](https://www.w3.org/TR/owl-time/#topology#time:Interval)` and `[:Instant](https://www.w3.org/TR/owl-time/#topology#time:Instant)`, and they are the only two subclasses of `[:TemporalEntity](https://www.w3.org/TR/owl-time/#topology#time:TemporalEntity)`. Intervals are things with extent. Instants are point-like in that they have no interior points, but it is generally safe to think of an instant as an interval with zero length, where the beginning and end are the same.

This idea - that time intervals are the more general case and time instants are just a limited specialization - is the first key contribution of Allen's analysis.

The class `[:Interval](https://www.w3.org/TR/owl-time/#topology#time:Interval)` has one subclass `[:ProperInterval](https://www.w3.org/TR/owl-time/#topology#time:ProperInterval)`, which corresponds with the common understanding of intervals, in that the beginning and end are distinct, and whose membership is therefore disjoint from `[:Instant](https://www.w3.org/TR/owl-time/#topology#time:Instant)`.'

##  Issues

- annotations only, no temporal reasoning intended [^1]
- suffers from class-as-instance modelling confusion [^1]
- ambiguity problems, see [[ar.modelling-time-within-a-strongly-typed-database#^rpdqex91m56q]]

### what are OWL-Time's notorious ambiguity problems

@chatgpt.4: 

OWL-Time, part of the Semantic Web technology stack, is an ontology for describing the temporal content of web pages and the temporal properties of web services. It's designed to facilitate the use of time and temporal relations in RDF (Resource Description Framework) and OWL (Web Ontology Language) applications. However, like many complex ontologies, OWL-Time has its share of ambiguity issues, which can cause problems in its implementation and interpretation. Some of these issues include:

    Granularity and Precision: OWL-Time can represent time at various granularities, from years down to seconds or finer. However, ambiguities can arise when different parts of a system or dataset use different granularities or when there's a need to convert or compare times across different granularities. The precision of time representation can also be a source of ambiguity, especially in historical data or future projections.

    Time Zones and Localization: Time zone handling is a complex aspect of time representation. OWL-Time does not inherently resolve issues related to time zones, daylight saving time, or localization. This can lead to ambiguities when interpreting the exact moment an event occurred, especially in systems that are distributed across multiple time zones.

    Temporal Relations: OWL-Time defines a range of temporal relations (such as before, after, during, overlaps), but the interpretation of these relations can be ambiguous without clear context. For example, determining whether an event "during" another means it encompasses the entire duration of the other event or just a part of it can be unclear.

    Open vs. Closed Intervals: In OWL-Time, an interval can be defined with start and end times. However, there can be ambiguity about whether these intervals are open (excluding the start and end points) or closed (including them). This distinction can be crucial in some applications.

    Temporal Reference Systems: OWL-Time allows for the definition of various temporal reference systems (like Gregorian calendar, Julian days, etc.). However, ambiguities can arise when converting or comparing dates across different systems, or when systems have different ways of handling leap years, leap seconds, etc.

    Vagueness in Temporal Descriptions: Natural language descriptions of time are often vague (e.g., "in the morning," "soon," "recently"). Representing these concepts in a structured format like OWL-Time can be challenging and lead to ambiguities in interpretation.

    Integration with Non-temporal Data: Combining temporal data with non-temporal data can sometimes lead to ambiguities, especially when the temporal aspects are not explicitly defined or are defined using different standards or formats.

Addressing these ambiguities often requires additional context, clear definitions of terms, and sometimes custom extensions or interpretations of the OWL-Time ontology to fit specific use cases. In many practical applications, it's crucial to document how these ambiguities are resolved to ensure consistent understanding and processing of temporal data.

### from gUFO perspective

from https://github.com/nemo-ufes/gufo/issues/48#issuecomment-3631515472 :

"Ideally, the whole time:TemporalEntity taxonomy would go under gufo:AbstractIndividual, as this is how we best interpreted the ontological nature of time instants and intervals in that specification.

However, there are two excerpts of the specification which are problematic (I've added emphasis in bold):

    The properties :hasTemporalDuration, :hasBeginning and :hasEnd, together with a fourth generic property :hasTime, support the association of temporal information with any temporal entity, such as an activity or event, or other entity.

and:

    The PROV-O classes prov:Activity and prov:InstantaneousEvent may be conceived as sub-classes of :TemporalEntity and :Instant respectively.

prov:Activity           rdfs:subClassOf    time:TemporalEntity .
prov:InstantaneousEvent rdfs:subClassOf    time:Instant .

We understand activities and events as concrete individuals. So, in the end, OWL-Time does not clarify the ontological nature of its temporal entities (instants included). This is unfortunate for that specification (and we'd hope it would be fixed simply by omitting these excerpts above)."


## References

[^1]: [[book.an-introduction-to-ontology-engineering-keet#^k691d5r7ug82]]