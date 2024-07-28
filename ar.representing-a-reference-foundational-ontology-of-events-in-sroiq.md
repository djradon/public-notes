---
id: b5r5h1ckc8ip13synq0lpjw
title: Representing a Reference Foundational Ontology of Events in Sroiq
desc: ''
updated: 1722055198256
created: 1721071043934
---

- https://content.iospress.com/download/applied-ontology/ao190214?id=applied-ontology%2Fao190214
- topics: [[prdct.alloy-specification-language]] [[prdct.sroiq]] [[prdct.unified-foundational-ontology.ufo-b]]

## Abstract

- In recent years, there has been a growing interest in the application of foundational ontologies, i.e., formal ontological theories in the philosophical sense, to provide a theoretically sound foundation for improving the theory and practice of conceptual modeling and knowledge representation. This paper addresses one particular foundational theory of events termed UFO-B, which has been successfully employed as a reference model for addressing problems from complex media management, enterprise architecture, software engineering, and modeling of events in petroleum exploration. Despite its success, there is still no formalization of UFO-B in a decidable knowledge representation language that could support reasoning about complex events and event relations. We address this gap by proposing a number of alternative translations from UFO-B’s original axiomatization (in first-order logic and in the Alloy formal language) to the description logic SROIQ, which is the formal underpinning of OWL 2 DL. Additionally, to support practical applications, we translated these SROIQ theories to OWL 2 DL TBoxes, which were validated by showing that all the intended models of UFO-B (the logical models of the UFO-B specification in Alloy) that we generated are consistent with these UFO-B TBoxes. In a sense, the specification in Alloy implements the specification in first-order logic, while the OWL 2 TBoxes implement the SROIQ specifications. Incidentally, the methodology that we designed for the translation from UFO-B’s original axiomatization in FOL and Alloy to SROIQ came to be a key contribution of this work by providing us evidence of the inadequacy of DLs for the specification of comprehensive foundational ontologies.

## Highlights

- the expressive power of OWL-like languages is rather restricted and too limited for expressing relational aspects of formal ontology as well as aspects that go beyond what can be formulated as a classification problem (Bittner and Donnelly, 2007).
- it is widely believed that the language of first order predicate logic is sufficiently powerful for formalizing formal ontologies (Smith, 2003). This may be true. The aim of this paper is it, however, to make the case that for the development, the presentation, and the computer-assisted verification of formal ontologies the usage of higher-order languages and associated tools is highly beneficial.
- uses Isabelle/HOL/Isar (Paulson and Nipkow, 2017; Paulson, 1994; Nipkow, 2003) 
  - [[prdct.hol]] 