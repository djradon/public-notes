---
id: yc40keh2zrpwnsyolhp1md1
title: PROV-O
desc: 'the Provenance Ontology provides a set of classes, properties, and restrictions that can be used to represent and interchange provenance information'
updated: 1730072361636
created: 1712534043697
---

- https://www.w3.org/TR/prov-o/
- [[c.ontology.creative-work]] [[c.ontology.domain]]
- rdfs:isDefinedBy http://www.w3.org/ns/prov# 
- implicit accessURL of https://www.w3.org/ns/prov-o
- versionIRI http://www.w3.org/ns/prov-o-20130430


## Terms

### Bundle

- a named set of provenance descriptions, and is itself an Entity, so allowing provenance of provenance to be expressed


## Thoughts

- ontology IRI is http://www.w3.org/ns/prov although that houses other things too, seems like it should be https://www.w3.org/TR/prov-o/
- can't re-use :category because it's an annotation property

## Issues

- prov:generatedAtTime and prov:invalidatedAtTime seem to point to valid time, but feel like system time in the examples 


## References

- https://www.w3.org/TR/prov-o/#description-starting-point-terms
- https://s11.no/2013/prov/resources-that-change-state/