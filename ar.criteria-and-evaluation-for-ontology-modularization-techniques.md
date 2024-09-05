---
id: 7ilgt9f2hlvzn5ikinj086z
title: Criteria and Evaluation for Ontology Modularization Techniques
desc: ''
updated: 1725518926232
created: 1725517585004
---

- http://publications.wim.uni-mannheim.de/informatik/lski/dAquin10CriteriaChapter.pdf

## Summary

While many authors have argued for the benefits of applying principles of modularization to ontologies, there is not yet a common understanding of how modules are defined and what properties they should have. In the previous section, this question was addressed from a purely logical point of view. In this chapter, we take a broader view on possible criteria that can be used to determine the quality of a modules. Such criteria include logic-based, but also structural and application-dependent criteria, sometimes borrowing from related fields such as software engineering. We give an overview of possible criteria and identify a lack of application-dependent quality measures. We further report some modularization experiments and discuss the role of quality criteria and evaluation in the context of these experiments.


## Highlights

### Introduction

#### Scenarios

- ontology partitioning (a set of modules that form the original)
- selective use and re-use ( a smaller part of an ontology that covers certain aspects of the domain is identified as a basis for a specific application.)

### Use Cases for Modularization

- maintenance
- publication (solution-specific subsets)
- validation (experts have to fit the ontology into their brain)
  - What is missing is an abstracted view on the overall model and its structure as well as the possibility to focus the inspection of a specific aspect
- processing, aka scalability

### Modularization Approaches

#### Partitioning Approaches

- some approaches being labeled as partitioning methods do not actually create partitions, as the resulting modules may overlap.

#### Module Extraction Approaches

- traversal approach: starting from the elements of the input sub-vocabulary, relations in the ontology are recursively “traversed” to gather relevant (i.e. related) elements to be included in the module.
  - Such a technique has been integrated in the [[prdct.protege.prompt]] tool

###  Evaluation Criteria for Modularization

#### Logical Criteria


