---
id: u69ohenrjzegyb4ta4bp07j
title: Basic Formal Ontology
desc: >-
  a small, upper-level, realist, bicategorial ontology that is designed for use in supporting information retrieval, analysis and integration in scientific and other domains
updated: 1730762652373
created: 1696610915530
---

- [[c.ontology.upper]]
- url: https://basic-formal-ontology.org/ https://raw.githubusercontent.com/BFO-ontology/BFO/master/bfo.owl
- repo: https://github.com/bfo-ontology/BFO/
- #docs https://github.com/bfo-ontology/BFO/wiki
- #similar [[prdct.gist]]
- related: [[prdct.common-core-ontologies]]

![](/assets/images/2023-10-10-11-37-53.png)

## Description

- "The Basic Formal Ontology (BFO)6 sees Ontology as reality representation. It aims at reconciling the 3-dimensionalist and 4-dimensionalist views with a ‘Snap’ ontology of endurants, which is reproduced at each moment of time and is used to characterize static views of the world, and a ‘Span’ ontology of happenings and occurrents and, more generally, of entities which persist in time by perduring. It has a limited granularity and is heavily influenced by parthood relations, boundaries, dependence."
- "BFO grows out of a philosophical orientation which overlaps with that of DOLCE and SUMO. Unlike these, however, it is narrowly focused on the task of providing a genuine upper ontology which can be used in support of domain ontologies developed for scientific research, as for example in biomedicine within the framework of the OBO Foundry. Thus BFO does not contain physical, chemical, biological or other terms which would properly fall within the special sciences domains. BFO is the upper level ontology upon which OBO Foundry ontologies are built.

## Issues

- monohierarchy
- IRIs aren't human-readable, e.g. http://purl.obolibrary.org/obo/BFO_0000015
- "only continuants – and hence not occurrents – are allowed to have qualities."

- entity
  - continuant: exists through time, i.e. "three-dimensionalist"
    - independent continuant: doesn't require a bearer, e.g. 
      - material entity
        - object
        - fiat object part: arm (it's not an object b/c it reflects decision)
        - object aggregate
      - immaterial entity
        - site (e.g. holes)
        - continuant fiat boundary
          - fiat point (zero-d)
          - fiat line (1d)
          - fiat surface (2d)
        - spatial region
          - 0d, 1d, 2d, and 3d
    - generically dependent continuant
    - specifically dependent continuant
      - qualities: not realizable (like redness)
      - realizable entity: a potential, or function, like the ability of a phone to make phone calls
        - role
        - disposition
          - function
  - occurrent
    - process
    - process boundary
    - temporal regional
    - spatiotemporal region

## Attributes

- **realist**: all classes have (or had) instances in space and time
  - fictional world ontologies are built by mimicking existing BFO-conformant ontologies"
- **backbone taxonomy + lateral relations** : 

## [BFO2 Reference](https://raw.githubusercontent.com/BFO-ontology/BFO/master/docs/bfo2-reference/BFO2-Reference.pdf) 

- We use ‘category’ to refer to those universals at the most general and domain-neutral level. BFO treats only of categories in this sense. A category is a formal (= domain-neutral) universal, as contrasted with the material (domain-specific) universals represented in one or other domain ontology. BFO:fiat object part is a category in this sense; not however organism or weapon, or mortgage contract. Spatial, temporal and spatiotemporal region terms are counted as representing formal universals in this sense, since they apply in all domains.
- is_a hierarchy
- specifically dependent continuants are subject to the axiom of non-migration – they cannot migrate from one bearer to another. Generically dependent continuants, in contrast, can in a sense migrate, namely through a process of exact copying which allows, for example, the very same information artifact to be saved to multiple storage devices.
![[#comparison gist Council 12-1-22 - gist/BFO comparison with Dylan Abney|prdct.gist#comparison-gist-council-12-1-22---gistbfo-comparison-with-dylan-abney]]

## Resources

- [[ar.bfo-2-0-specification-and-users-guide]]
- https://therecouldbebadgers.wordpress.com/2018/06/27/endurants-perdurants-continuants-occurrents/
- [[ar.basic-formal-ontology-july-2023]]
- [[prdct.bfo-classifier]]
- [[book.building-ontologies-with-basic-formal-ontology]]

## References

- https://www.youtube.com/watch?v=uflMfvI-ZxI
- [[ar.foundational-ontologies-in-action]]
- https://eng.libretexts.org/Bookshelves/Computer_Science/Programming_and_Computation_Fundamentals/An_Introduction_to_Ontology_Engineering_(Keet)/07%3A_Top-Down_Ontology_Development/7.02%3A_Foundational_Ontologies
- https://raw.githubusercontent.com/BFO-ontology/BFO/master/docs/bfo2-reference/BFO2-Reference.pdf
- [[community.google-groups.bfo-discuss.entity-to-particular]]