---
id: o99h4umwihpwctxh1uwle9u
title: Valid Time RDF
desc: 'VTRDF and VT-SPARQL,'
updated: 1722728690772
created: 1711033114556
---

- url: https://academicworks.cuny.edu/cgi/viewcontent.cgi?article=5097&context=gc_etds

## Log

- t.2024.04.01.11: re-reading this on the plane, I'm amazed how much more helpful and concrete this seems now.
- t.2024.07.24.13 as much as I want it, I'm concerned that valid time is not existence time.
  - at the very least, it shouldn't mean birth-death
    - what if John comes back from the dead?
  - in an immutable data store, valid time needs to be reserved for "this fact was considered valid", from interpretation of "database"
  - doesn't make sense to apply vt to (some) resources, because they are eternal
  - if we use relators, same thing
  - singleton predicates, maybe
  - classic predicates/properties might be interesting... valid time properties 
  - you still need a way to refer to resources/entities at a given time, but probably an instant not an interval. 

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

- [[Batsakis|user.sotiris-batsakis]] et al. extended 4D Fluents model to incorporate qualitative temporal relations that have unknown temporal information... Semantics of the extended 4D Fluents model is based on the original 4D Fluents model, with the additional temporal semantics needed for qualitative temporal relations.

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
    - t.2024.08.03.16 seems like you could use SWRL or 

## Valid Time RDF

- In this thesis, we adopt a modeling approach that employs ideas from the 4D view and originated from the study in [66], and propose the Valid Time RDF, or [[prdct.vtrdf-valid-time-rdf]] in short
- VTRDF is based on temporal resource and temporal relationship or temporal fact.
  - **temporal resource**: RDF-compliance resource equipped with a timestamp to denote its existence in time
    - Each temporal resource is a coalesce of all its temporal parts
      - i.e. wholly present during its existence in time
    - Temporal parts are derived by slicing or projecting a temporal resource on to the time dimension.
  - **temporal relationship**: a factual assertion that relates qualified temporal resources, formed between either temporal parts or temporal resources provided that the participating parts or resources coexist in time
- We introduce VTR, an infinite set of valid time resources, as the building block for VTRDF triples and VTRDF graphs ^6x6gy39e5d24
  -  valid time resource is a resource with its existence time or valid time
  -  In VTRDF, we consider a valid time resource as a collection of all its temporal parts.
  -  Assertions can be made with respect to both the collection and any individual temporal part.
  -  A temporal resource is a master resource, whereas all its temporal parts are member resources.
  -  Projections from the master resource to its temporal parts are possible via projection functions.
  -  The temporal aspects of the resources can use valid time, transaction time, or bitemporal.
     -  In this research, we focus on the valid time.
     -  Hence, we would use valid time resources and temporal resources interchangeably as appropriate

### Notations, Namespace, and Time Domain

- vtrdf: and vtrdfs: refer to the namespace of VTRDF vocabulary and VTRDF Schema vocabulary
- While the symbol # is used to denote an additional part of the primary resource in the standard RDF model, VTRDF requires a second fragment identifier to accommodate the valid time dimen- sion.
  - t.2024.07.24.11 with slash IRIs, could work too
  - The symbol • is used as a delimiter that separates the first fragment identifier from the valid
- T is the set of time points with a linear order less-than (<). For simplicity, we use the standard U.S. calendar dates as the unit of time points in the format of month/day/year, such as 1/10/1995
- Tɪ is the set of time intervals defined over T
- 0 is the lower bound of the time axis whose interpretation is open for user’s need of data
modeling.
- now is a special constant that represents the current time. Its value will change as time
advances.
- ∞ is a constant that represents the upper bound of the time axis.
- [0, ∞] is a special interval used to represent the maximal interval

### Running Example

- John enrolled in the Semantic Web course
(SW), lived in New York City (NYC), and had a valid time [2/1/2016, 5/31/2016).
  - t.2024.07.24.12 kinda weird choice, seems like enrolled and livedIn are unrelated
![](/assets/images/2024-07-24-12-52-39.png)


### Definitions

#### valid time IRI

- a valid time IRI consists of:
  - resource
  - valid time
  - http://example.org/temporal-SW#John•[01-10-1995–now]

####  Valid Time Literal

- Let L be an infinite set of standard literals, [0, ∞] the maximal interval, and V T L = L × [0, ∞]
be the Cartesian product.
-  A valid time literal lt ∈ V T L represents a literal that is always valid in
time.
  - That is, all literals assume a default maximal interval [0, ∞] unless otherwise specified.

#### Valid Time Data Type

- Let D be an infinite set of standard data types, [0, ∞] the maximal interval, and V T D =
D × [0, ∞] be the Cartesian product. A valid time data type dt ∈ V T D is a data type recognized
in the standard RDF with a default maximal interval [0, ∞].
  - Valid time data types are used to annotate valid time literals.
  - A special data type vtrdf:langString[0, ∞] can also be used to denote a language-tagged string value.

#### Lexical-to-Value Mapping Function V T L2V

- V T L2V is a partial mapping from the lexical space of valid time literals to the value space V. A valid time literal lt with a valid time data type dt denote the mapped value obtained from the value space. That is, V T L2V (lt, dt) = v where v ∈ V.


#### Valid Time Property

- Let P be the set of any properties, including those defined in RDF and RDFS vocabularies [16], TI be the set of intervals, and V T P = P × TI be the Cartesian product of them. A valid time property pt ∈ V T P is any property that is valid during a specified interval i ∈ TI .

#### Valid Time Blank Node

- Let B be an infinite set of blank nodes, TI be the set of intervals, and V T B = B × TI be the Cartesian product. A valid time blank node bt ∈ V T B denotes the existence of a resource whose valid time may or may not be known. For simplicity, every valid time blank node in the VTRDF model assumes a default maximal valid interval [0, ∞] unless otherwise specified. A valid time blank node is usually identified by a local identifier.

#### Valid Time Resource Projection Function

- A valid time resource projection function...

#### Valid Time RDF Triple

A Valid Time RDF triple (st, pt, ot) satisfies the temporal constraint, called Temporal Triple Integrity,such that pt is bounded by the interval that is formed by the common valid time of st and ot.
  - In other words, the temporal triple integrity requires that a valid time relationship can only be established between two existing resources with non-disjoint valid time

#### Predicate Defining Time (PDT) and Resource Modeling Time (RMT)

- rt takes PDT when it is used in a VTRDF triple as a predicate to define the time of a re- lationship. In this case, PDT corresponds to the interval during which the relationship is valid
- rt takes RMT when it is used in a VTRDF triple as a subject or an object that eventually involves in a relationship.
  - "RMT is the time that we want to store about the facts into the database."???

#### Valid Timeslice Operator

- Given a VTRDF graph Gt and an interval i = [l, u), the valid time slice operator, TS, returns a temporal subgraph of Gt at i
![](/assets/images/2024-07-24-12-55-11.png)
  - t.2024.07.24.12 i.e., it cuts everything down to the interval)

#### VTRDF Subgraph

- in addition to the common-sense definition, a "valid timeslice of a VTRDF graph Gt is a **temporal subgraph** of it."
- ![](/assets/images/2024-07-24-12-53-09.png)
  - t.2024.07.24.12 is it a typo that fig 4.3 has "now" and fig.4.5 has "infinity"

#### VTRDF Underlying Triple/Graph

- basically, de-temporalizing
- "If two or more triples agree on the subject or object, they are combined to one triple. "
  - t.2024.07.24.13 typo, should be "subject and object"

#### VTRDF Graph Vocabulary

- the set of valid time IRIs that appear in Gt excluding valid time literals.

#### Ground VTRDF Graph

- no valid time blank nodes


### VTRDF Vocabulary

- VTRDF Vocabulary is formulated as layers and RDF-compliant.
- 