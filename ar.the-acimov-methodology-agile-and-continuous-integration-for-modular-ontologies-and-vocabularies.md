---
id: qv2k0ar4j0ef1meop2bzigz
title: >-
  The Acimov Methodology Agile and Continuous Integration for Modular Ontologies
  and Vocabularies
desc: ''
updated: 1712849614451
created: 1712783360619
---

- https://www.emse.fr/~zimmermann/Papers/mk2023.pdf
- topics: [[t.km.ontology.modular]]

## Abstract

- This work describes the Agile and Continuous Integration for Modular Ontologies and Vocabularies (ACIMOV) ontology engineering methodology for developing ontologies and vocabularies. ACIMOV extends the SAMOD agile methodology to (1) ensure alignment to selected reference ontologies; (2) plan module development based on dependencies; (3) define ontology modules that can be specialized for specific domains; (4) empower active collaboration among ontology engineers and domain experts; (5) enable application developers to select views of the ontology for their specific domain and use case. ACIMOV adopts the standard git-based approach for coding, leveraging agility and DevOps principles. It has been designed to be operationalized using collaborative software development platforms such as Github or Gitlab, and tooled with continuous integration and continuous deployment workflows (CI/CD workflows) that run syntactic and semantic checks on the repository, specialize modules, generate and publish the ontology documentation.


## Highlights

### Agile ontology engineering methods

Many ontology engineering methodologies have been proposed over time, including METHONTOLOGY [ 9], On-To-Knowledge [ 10], DILIGENT [ 11 ], the “Ontology Development 101” [ 12], NeOn [ 13]. Some directly transpose software engineering methodologies, for example UPON Lite [ 14] is based on Rational Unified Process. The LOT methodology [ 15] adopts a V-model approach with conditional feedback at upstream development stages. Other early methods pro- posed to rely and align with existing ontologies to bootstrap new ontologies as in SENSUS [16 ]. More recently, methodologies are inspired by the principles of Agile software engineering, which promote collaboration between developers and stakeholders by producing regular updates of the product1. Among these methods, AMOD [ 17 ] and CD-OAM [ 18 ] are based on SCRUM. AMOD is the first method that describes the cycle of ontology development in a SCRUM sprint. CD-OAM enriches AMOD by describing the management the ontology commitment user community. XPOD [ 19 ] and eXtreme ontology method [ 20] are based on eXtreme Programming. The Lean Ontology Development (LOD) [21] is inspired by the Lean approach: Build-Measure- Learn. SAMOD [ 1 ] is revisiting the motivating scenarios and competency questions of Uschold and Gruninger [22], additionally considering ontology modules and test-driven development.

### Git and CI/CD for ontology engineering

Before the democratization of these frameworks, a few preliminary approaches such as VoCol [ 23 ] or OnToology [ 24] were proposed in the ontology engineering community using Github applications2. [[prdct.ontology-development-kit]] (ODK) [ 25] uses Travis CI to run workflows with the ROBOT tool [ 26 ] developed by the Open Biological and Biomedical Ontologies (OBO) community. CI/CD pipelines are reported for the publication of different ontologies, such as the Financial Industry Business Ontology (FIBO) in [ 27], the International Data Spaces Information Model (IDSA) in [ 28], and the CASE Cyber Ontology3. Specific Github actions are available on the Github marketplace for running RDFLint4, validating RDF syntaxes5,6, or validating RDF files against SHACL shapes7 or ShEx [29].

## Methodology

Step 1 Collect requirements and identify reference ontologies.
Step 2 Review meeting (an event)
Step 3 Select relevant modules from reference ontologies
Step 4 Manage modelet backlog
Step 5 Modelet development meeting (an event)
Step 6 Develop and test modelets
Step 7 Integrate modelet and release ontology artifacts


