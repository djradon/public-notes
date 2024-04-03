---
id: fiam26zpn6ka48mcm86buu1
title: Deeponto
desc: ''
updated: 1712160761952
created: 1712160608110
---

- repo: https://github.com/KRR-Oxford/DeepOnto

## Background

- relies on [[prdct.owlapi]] version 4.5.22 (written in Java) for ontologies.

We follow what has been implemented in mOWL that uses JPype to bridge Python and Java Virtual Machine (JVM). Please check JPype's installation page for successful JVM initialisation.
Pytorch

relies on Pytorch for deep learning framework.

## Features

Ontology Reasoning ([OntologyReasoner][deeponto.onto.OntologyReasoner]): Each instance of DeepOnto has a reasoner as its attribute. It is used for conducting reasoning activities, such as obtaining inferred subsumers and subsumees, as well as checking entailment and consistency.

Ontology Pruning ([OntologyPruner][deeponto.onto.OntologyPruner]): This sub-module aims to incorporate pruning algorithms for extracting a sub-ontology from an input ontology. We currently implement the one proposed in [2], which introduces subsumption axioms between the asserted (atomic or complex) parents and children of the class targeted for removal.

Ontology Verbalisation ([OntologyVerbaliser][deeponto.onto.OntologyVerbaliser]): The recursive concept verbaliser proposed in [4] is implemented here, which can automatically transform a complex logical expression into a textual sentence based on entity names or labels available in the ontology. See verbalising ontology concepts.

Ontology Projection ([OntologyProjector][deeponto.onto.OntologyProjector]): The projection algorithm adopted in the OWL2Vec* ontology embeddings is implemented here, which is to transform an ontology's TBox into a set of RDF triples. The relevant code is modified from the mOWL library.

Ontology Normalisation ([OntologyNormaliser][deeponto.onto.OntologyNormaliser]): The implemented

normalisation is also modified from the mOWL library, which is used to transform TBox axioms into normalised forms to support, e.g., geometric ontology embeddings.

Ontology Taxonomy ([OntologyTaxonomy][deeponto.onto.OntologyTaxonomy]): The taxonomy extracted from an ontology is a directed acyclic graph for the subsumption hierarchy, which is often used to support graph-based deep learning applications.
