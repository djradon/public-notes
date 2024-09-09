---
id: bgo1umvoasmlbvq3cie4hzj
title: An Extensible Approach to Multi Level Ontology Modelling
desc: ''
updated: 1725666578731
created: 1725511917090
---

- https://www.scitepress.org/PublishedPapers/2021/106842/106842.pdf

## Highlights

### Introduction

- in the Vertebrate Taxonomy Ontology (VTO) (Phenoscape, 2021) and the NCBI Taxonomy (NCBI, 2021), all biological species are modelled as classes
- In contrast, in the Wildlife Ontology (WO) (BBC, 2021) and in the Global Biodiversity Information Facility (GBIF, 2021), biological species are modelled as instances.
  - The authors of the WO state on (BBC, 2021): “One perennial problem associated with modelling biological taxonomies using RDF is whether to attempt to model individual species as classes, or whether to simply model species as instances of a generic Species class. The latter approach is simpler and avoids creating a huge ontology that attempts to model all biological organisms. Existing ontologies have taken different approaches to resolving this issue, some choosing one style, others another. At present there doesn’t seem to be a consensus. With this in mind, the Wildlife Ontology adopts the simpler of the two approaches, i.e. modelling species as instances of a Species class, as this maximises interoperability with many of the existing Linked Data sources, particularly dbpedia, which adopt similar approaches.”
- **The contribution of this paper is a modelling approach which rigorously utilizes multi-facet (Atkinson and Kühne, 2001; Neumayr et al., 2009; Frank, 2014) behaviour, an aspect of multi-level modelling, allowing entities to be modelled as classes (class facet) and instances (instance facet) simultaneously**

### Related Work

- classes are described as groups of resources and instances as their members. 
- @dean-allemang calls the reaction of defining everything as classes "rampant classism"
  - "We agree with them"
- (Noy and McGuinness, 2021) [[ar.ontology-development-101-a-guide-to-creating-your-first-ontology]]: A criterium they define for the decision to model something as a class or an instance is the lowest level of granularity in the representation.
  - i.e., individual instances are the most specific concepts represented in a knowledge base
- various authors recommend modelling pairs of classes where a class is associated with a corresponding type class
  - modelling pattern is called materialization pattern
  - the term powertype is used in (Odell, 1994) and (Guizzardi, et al., 2015). ^vt540o589i6g
- With conventional modelling approaches it is not possible to mix the properties of base class and its powertype into one class, since it makes no sense to have a property Number_Plate for a Car_Model.
- **Our approach is simpler insofar as it does not require separate entities Car and Car Model while still explicitly distinguishing between the different facets.**
- Another approach to avoid separate entities Car and Car Model is described in (Neumayr et al. 2009), called Multi-Level Domain Modeling. Properties are annotated with meta attributes which define rules for inheritance and instantiation. E.g. for the base class Car the data property maxSpeed is annotated with :model to refer to a Car_Model while the data property Milage is annotated with :physical_entity to refer to an individual car. This allows merging the properties of Car and Car_Model into only one class Car while keeping the semantics of the properties clear.
- In a comparable approach (Frank, 2014), level numbers are assigned to properties. For Car the property Milage would be defined with level=0 which corresponds to the :physical_entity annotation in (Neumayr et al. 2009), while maxSpeed would be annotated with level=1 which corresponds to the :model annotation. Annotating properties with multiple levels or with different levels for different contexts is not possible, as is enabled in our approach.
- In (Brasileiro et al., 2016a), a fixed separation of entities into individuals, 1 st order type, 2 nd order type and 3 rd order type is proposed. Our approach is more flexible as it allows context-dependent viewpoints.
- 

## References

- [[book.practical-ontologies-for-information-professionals]]