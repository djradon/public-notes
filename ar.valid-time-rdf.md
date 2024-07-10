---
id: o99h4umwihpwctxh1uwle9u
title: Valid Time RDF
desc: 'VTRDF and VT-SPARQL,'
updated: 1720631866058
created: 1711033114556
---

- url: https://academicworks.cuny.edu/cgi/viewcontent.cgi?article=5097&context=gc_etds


## Highlights

### Instantiating-Identifying Concept/Relationship (IIR)

In IIR models, a concept or relationship is reified and further temporalized. Either such relationship is abstracted as a new object, or a concept is viewed as four dimensional and instantiated to have temporal extents. Singleton Property converts each relationship to be universally unique. 4D fluents use concepts that view each resource as a perdurant. Fluents represent properties that change over time

#### Singleton Property

The formal semantics of the singleton property is derived from the standard RDF and RDFS semantics with the additional semantics extension for the vocabulary rdf:singletonPropertyOf. The singleton property gives rises to three cases of query patterns: data, metadata and mixed patterns which SPARQL supports. 

#### 4D Fluents

- Perdurantism is a philosophical theory of persistence and identity [34], and it is closely related to four dimensionalism. In the four dimensional view, an object that persists through time has distinct temporal parts at every time instant through its existence in time. Furthermore, each persisting object can be considered a four dimensional spacetime worm that stretches across space-time. Slicing the worm at a specific time interval or instant of the time dimension yields a temporal part.
  - t.2024.03.21.08: and endurant 
- Fluent is a component of [[t.phil.logic.situational-calculus]]
![[t.phil.logic.situational-calculus#^vmhpi7mrf12z]]
![](/assets/images/2024-04-01-11-15-48.png)
- "OWL inverse operator and cardinality constraints are available and standard OWL reasoners can be used for inferencing."

#### Extended 4D Fluents 

- Batsakis et al. extended 4D Fluents model to incorporate qualitative temporal relations that have unknown temporal information... Semantics of the extended 4D Fluents model is based on the original 4D Fluents model, with the additional temporal semantics needed for qualitative temporal relations.

![](/assets/images/2024-04-01-11-24-36.png)

#### Temporal Web Ontology Language

- [[prdct.owl.towl]]

#### Valid-Time Temporal Model

- O’Connor et al. propose a valid-time temporal model and a SWRL-based [40] query mechanism for manipulating temporal knowledge in OWL ontologies
- In the valid-time temporal model, any existing OWL class can have temporal aspects as long as it subclasses temporal:Fact, which is the super class of all temporal facts. This avoids significant ontology rewriting in converting an ontology to a temporal version.
- The temporal expressivity of this model is further enhanced by using SWRL [40] to construct temporal rules. A set of temporal operators that includes Allen’s operators [4] is implemented as library-like built-ins for SWRL rules.
- Querying the temporal ontology is done by [[prdct.sqwrl]]

#### Named Graphs

- all triples share the same temporal extent are grouped in the same graph
- In an extreme case that each triple requires a different time reference, a significant
amount of named graphs is needed. 
- When triples may need multiple metadata annotation, using Named Graphs model becomes complex.
- τ SPARQL 

## RDF+ 

RDF+ model [62] uses named graphs and triple-level identifiers. Named graphs are used in place of RDF reification. Triple identifiers allow explicit annotation of meta knowledge. RDF+ model has two type of statements: literal and meta knowledge statement. A RDF+ literal statement is a quintuple form (g, s, p, o, θ) where g is the graph’s IRI, s,p,o are standard RDF triple compo- nents, and θ is a statement identifier. Based on the triple identifier in the RDF+ literal statement, the RDF+ meta knowledge statement can be formed as (θ, π, ω). θ is the literal statement identi- fier, π is the meta knowledge property and ω is the range value of π. The set K of RDF+ literal statements and the set M of RDF+ meta knowledge statements constitute a RDF+ theory, 

## Discussion

- There are two temporal models in Instantiating-Identifying Concept/Relationship models. 4D Fluents [73, 6, 7] introduces temporal part for an entity changing over time. Each temporal part corresponds to a distinguishable timestamp. A fluent property associates two temporal parts. On the other hand, Singleton Property [52] ensures every relationship to be universally unique. As a result, an ordinary relationship, such as enrolled, becomes a relationship type.

## Valid Time RDF

- "As a result, a binary relationship actually incurs three timestamps: the valid
time of the relationship and two participating entities."
  - t.2024.07.10.10 really? Do entities have timestamps? John might have a birth and death, but relationships involving John don't need to know that. 
  - Also, birth-death are not the same as valid. 
  - There's an asymmetry with valid time in open-world. if there's no valid-to, can you assume ***now***? not in open-worlds. If there's no valid-from, you just assume it's missing. 

## Log

- t.2024.04.01.11: re-reading this on the plane, I'm amazed how much more helpful and concrete this seems now.