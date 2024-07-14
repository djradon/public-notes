---
id: zzoajb1hp4gezmidmjgeyll
title: >-
  Towards Ontological Foundations for Conceptual Modeling the Unified Foundational Ontology Ufo Story
desc: ''
updated: 1720931987248
created: 1713463627419
---

- https://drive.google.com/file/d/1w7hXNsX3JWdqXvGKTh7LUSyEjc-nYGcj/view?usp=drive_link
- authors: @giancarlo-guizzardi
- topics: [[prdct.unified-foundational-ontology]] [[t.km.ontology]]

## Abstract

This paper describes a long-term research program on developing ontological foundations for conceptual modeling. This program, organized around the theoretical background of the foundational ontology UFO (Unified Foundational Ontol- ogy), aims at developing theories, methodologies and engineering tools with the goal of advancing conceptual modeling as a theoretically sound discipline but also one that has concrete and measurable practical implications. The paper describes the historical context in which UFO was conceived, briefly discusses its stratified organization, and reports on a number of applica- tions of this foundational ontology over more than a decade. In particular, it discusses the most successful application of UFO, namely, the development of the conceptual modeling language OntoUML. The paper also discusses a number of methodological and computational tools, which have been developed over the years to support the OntoUML community. Examples of these methodological tools include ontological patterns and anti-patterns; examples of these computational tools include automated support for pattern-based model construction, formal model verification, formal model validation via visual simulation, model verbalization, code generation and anti-pattern detection and rectification. In addition, the paper reports on a variety of appli- cations in which the language as well as its associated tools have been employed to engineer models in several institutional contexts and domains. Finally, it reflects on some of these lessons learned by observing how OntoUML has been actually used in practice by its community and on how these have influenced both the evolution of the language as well as the advancement of some of the core ontological notions in UFO

## Highlights

- our first attempt was to unify DOLCE and GFO to produce a reference founda- tional ontology for conceptual modeling (hence, the name Unified Foundational Ontology) (Guizzardi & Wagner, 2004). Both theories were philosophically sound and formally characterized. Moreover, they were both based on the so-called Aristotelian Square, i.e., “Four-Category Ontologies”.
- ontological foundations for conceptual modeling would demand micro-theories to address conceptual modeling’s most fundamental constructs, namely, Entity Types and Relationship Types (hence, the name of the so-called Entity-Relationship ap- proach that gives the name to the most important conference in conceptual modeling!). So, any reference theory for conceptual modeling would need a rich theory of entity (object) types and a rich theory of domain (also called material) relations. In the case of the former, we needed something in the spirit of the ontology of universals underlying the OntoClean methodology (Guarino & Welty, 2009) in order to systematize a number of notions that were pervasive in the conceptual modeling literature (e.g., types, roles, phases or states, mixins) but for which there were no precise definitions or consensus (Guizzardi et al., 2004a). 
  - GFO’s theory of universals still does not recognize these notions and DOLCE does not include universal as a category (DOLCE was designed as an ontology of particulars).
    - DOLCE still does not include a theory of particularized relational properties (relational qualities) and the GFO theory of relations is subject to the so-called Bradley Regress (Bradley, 1893) and, hence, it can only be instantiated by infinite (logical) models. This feature makes it unsuitable for conceptual modeling applications. 
- Finally, there were many additional specific aspects needed for a general ontology for conceptual modeling that were not addressed by the existing approaches (e.g., attributes and datatypes, different types of specialization relations between relations, a rich theory of cognitively/linguistically motivated part-whole relations). We needed to develop a full-blown foundational ontology specifically created to address these conceptual modeling requirements