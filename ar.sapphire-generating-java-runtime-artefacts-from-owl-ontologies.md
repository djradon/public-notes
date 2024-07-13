---
id: fn2qciqpu028i9qujf46xxm
title: Sapphire Generating Java Runtime Artefacts from Owl Ontologies
desc: ''
updated: 1720735297840
created: 1720732182055
---

- https://simondobson.org/softcopy/sapphire-odise11.pdf
- topics: [[prdct.owl]] [[t.km.ontology]] [[prdct.sapphire]]
- authors: @graeme-stevenson @simon-dobson 

## Abstract

The OWL ontology language is proving increasingly popular as a means of crafting formal, semantically-rich, models of information systems. One application of such models is the direct translation of a conceptual model to a set of executable artefacts. Current tool support for such translations lacks maturity and exhibits several limitations including a lack of support for reification, the open-world assumption, and dynamic classification of individuals as supported by OWL semantics. Building upon the state-of-the-art we present a mapping from OWL to Java that addresses these limitations, and its realisation in the form of a tool, Sapphire. We describe Sapphire’s design and present a preliminary evalua- tion that illustrates how Sapphire supports the developer in writing concise, type safe code compared to standard approaches while maintaining competitive run- time performance with standard APIs.


## Highlights

- Mapping OWL Classes to Java interfaces is an established technique for approxi- mating OWL’s multiple inheritance [4, 5]. However, in generating implementation classes, schemes described in the literature provide no support for dynamic classifi- cation of OWL individuals.
- Puleston et al. [25] present a case study supporting an approach that conflates both domain-specific and ontology-agnostic aspects within a single API. Applications con- structed using this technique are assumed to be structured around a static core that is accessed in a domain-specific manner, with highly dynamic concepts at its edges that are accessed via a generic API.