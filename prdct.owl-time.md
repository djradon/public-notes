---
id: acxwjynzcfhybxyoe56el4i
title: Owl Time
desc: 'ontology of temporal concepts, providing a vocabulary for expressing facts about topological (ordering) relations among instants and intervals, together with information about durations, and about temporal position including date-time information'
updated: 1706739507242
created: 1701453829509
url: https://www.w3.org/TR/owl-time/
related: 
  - "[[prdct.vocab-owl-time-agg]]"
---

## Highlights

- "A set of ordered intervals (e.g. named dynasties, geological periods, geomagnetic reversals, tree rings) can make a simple form of temporal reference system that supports logical reasoning, known as an ordinal temporal reference system [iso19108]." 
- Four classes in the ontology support an explicit description of temporal position. `[:TemporalPosition](https://www.w3.org/TR/owl-time/#time:nominalPosition#time:TemporalPosition)` is the common super-class, with a property `[:hasTRS](https://www.w3.org/TR/owl-time/#time:nominalPosition#time:hasTRS)` to indicate the temporal reference system in use. `[:TimePosition](https://www.w3.org/TR/owl-time/#time:nominalPosition#time:TimePosition)` has properties to alternatively describe the position using a number (i.e. a temporal coordinate), or a nominal value (e.g. geologic time period, dynastic name, archeological era)

### Topological Temporal Relations

- 'The basic structure of the ontology is based on an algebra of binary relations on intervals (e.g., meets, overlaps, during) developed by Allen \[[al-84](https://www.w3.org/TR/owl-time/#topology#bib-al-84 "Towards a general theory of action and time. Artificial Intelligence 23, pp. 123-154.")\], \[[af-97](https://www.w3.org/TR/owl-time/#topology#bib-af-97 "Actions and events in interval temporal logic In: Spatial and Temporal Reasoning. O. Stock, ed., Kluwer, Dordrecht, Netherlands, pp. 205-245.")\] for representing qualitative temporal information, and to address the problem of reasoning about such information.

The ontology starts with a class `[:TemporalEntity](https://www.w3.org/TR/owl-time/#topology#time:TemporalEntity)` with properties `[:hasBeginning](https://www.w3.org/TR/owl-time/#topology#time:hasBeginning)` and `[:hasEnd](https://www.w3.org/TR/owl-time/#topology#time:hasEnd)` that link to the temporal instants that define its limits, and `[:hasTemporalDuration](https://www.w3.org/TR/owl-time/#topology#time:hasTemporalDuration)` to describe its extent. There are two subclasses: `[:Interval](https://www.w3.org/TR/owl-time/#topology#time:Interval)` and `[:Instant](https://www.w3.org/TR/owl-time/#topology#time:Instant)`, and they are the only two subclasses of `[:TemporalEntity](https://www.w3.org/TR/owl-time/#topology#time:TemporalEntity)`. Intervals are things with extent. Instants are point-like in that they have no interior points, but it is generally safe to think of an instant as an interval with zero length, where the beginning and end are the same.

This idea - that time intervals are the more general case and time instants are just a limited specialization - is the first key contribution of Allen's analysis.

The class `[:Interval](https://www.w3.org/TR/owl-time/#topology#time:Interval)` has one subclass `[:ProperInterval](https://www.w3.org/TR/owl-time/#topology#time:ProperInterval)`, which corresponds with the common understanding of intervals, in that the beginning and end are distinct, and whose membership is therefore disjoint from `[:Instant](https://www.w3.org/TR/owl-time/#topology#time:Instant)`.'

##  