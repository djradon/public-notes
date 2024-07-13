---
id: ub4u5ch2j5g63t9coa9x7k4
title: Owl Profiles Rule Based Reasoning and Handling Reasoning with the Jena API
desc: ''
updated: 1720773027918
created: 1720718593465
---

- https://www.dbis.informatik.uni-goettingen.de/Teaching/SWPr-SS20/f-jena-reasoning.pdf

## Highlights

- From practical considerations, the OWL profiles are more important:
http://www.w3.org/TR/owl2-profiles/
  – OWL2-EL: for ontologies that contain very large numbers of properties and/or classes.
  Basic reasoning problems can be performed in time that is polynomial with respect to
  the size of the ontology – not to the data
  – OWL2-QL: applications that use very large volumes of instance data, and where query
  answering is the most important reasoning task. Conjunctive query answering can be
  implemented using conventional relational database systems.
  – OWL-RL: scalable reasoning without sacrificing too much expressive power. OWL 2
  RL reasoning systems can be implemented using rule-based reasoning engines.

## OWL2-RL

- the DL-Prover [[prdct.hermit]] (DL only, no SPARQL) provides better functionality (than [[prdct.pellet]])for ontology
management.