---
id: nrkv4drjfk0hc0y7tmofrmw
title: tOWL
desc: 'Temporal Web Ontology Language'
updated: 1729848749847
created: 1718083662732
---

## Description

- Fransincar et al. proposed an extension of the OWL-DL language, called tOWL [49], for representing time and changes in an ontology. tOWL uses a subset of OWL-DL whose foundation is the logic SHIN (D). This logic is sufficiently expressive and is decidable for a sound and complete reasoning algorithm [45]. The time domain of tOWL handles both instants and intervals that are modeled by rational numbers and a set of partial order relations over them. As a result, an actual time instant, an interval or Allen’s temporal relations [4] are all converted to rational number-based equivalent instants or relations.  ^927zza20f03z
- For modeling changing values, tOWL employs the 4D Fluents model, i.e., perdurantist’s view [73]. tOWL is conceptualized as a layered approach. The foundation layer is OWL-DL and the extended concrete domain is the second layer. Time representation is at the third layer, which is defined by the concrete domain.
- Figure 3.7 gives the running example in tOWL. Note that tOWL requires separate intervals for :John and :SW. Therefore, a restriction on the equivalence of towl:interval1 and towl:interval2 is enforced by a relation towl:equal in Figure 3.7 which is one more triple used compared to 4D Fluents model in [73].
![](/assets/images/2024-10-25-02-30-44.png)
- In tOWL, the time domain is based on rational numbers and relations over them. This approach makes tOWL more expressive in representing complex temporal relations. For instance, in Figure 3.7, a temporal constraint towl:interval1 equates towl:interval2 can be expressed with the equality of endpoints of the two intervals.
- OWL reduces the proliferation of objects by differentiating types of fluents as FluentObjectProperty and FluentDatatypeProperty. For a Fluent- DatatypeProperty, which relates a time slice to a typed value, three triples can be saved due to that the time slice is not needed for a typed value. ^b8t2dt9958m2

## References

- [[ar.valid-time-rdf]]