---
id: jxej1bzfm42cbouwzcl0cd4
title: A Reusable Ontology for Fluents in Owl
desc: ''
updated: 1725998029503
created: 1722150651286
---

- https://www.researchgate.net/publication/221234960_A_Reusable_Ontology_for_Fluents_in_OWL
- authors: @christopher-welty
- published: 2006-01
- topics: [[t.phil.perdurantism]]


## Abstract

A critical problem for practical KR is dealing with relationships that change over time. This problem is compounded by representation languages such as OWL that are biased towards binary relations, even when the relationships that vary with time are binary. We discuss several approaches to this problem in OWL, and focus on the advantages of a four-dimensionalist (perdurantist) solution, which allows us to use more of the expressive power of the language.

## Highlights

- synchronic, i.e. it refers to only one point in time
- diachronic, vary with time
- we consider fluents to be relations that hold within a certain time interval and not in others.
- In the original formulation of fluents discussed by McCarthy&Hayes, another choice presented is to add a meta-logical predicate to relate the relationship to a time interval. 
  - e.g. holds(ceoOf(Sam, IBM), t 1 )
    - OWL does not allow relationships themselves to participate in relationships, which this would require.
- requirement: fluents are round-trip compatible with a representation in [[prdct.kif]] that uses *holds*
  - they perform "more advanced temporal reasoning" with a special-purpose plugin for [[prdct.jtp]]

### Solution Approaches for OWL

#### Reification

- turn each tuple in the extension of a relation into an object that itself has binary relationships, typically called
roles, identifying all the elements of the tuple
  - a reified relationship class, is created for each relation,
  - e.g. for ceoOf(Sam, IBM, t 1 )

```
Individual(IBM type(Company))
Individual(JohnsHopkinsUniversity type(University))
Individual(SamPalmisano type(Person))
Individual(Rel1 type(CeoOf)
value(CeoOf:ceo SamPalmisano)
value(CeoOf:company IBM)
value(CeoOf:holds t 1))
```

- Reification has a number of known problems that are outlined in more detail in [Noy and Rector, 2005]. 
  - None of these are serious, but they are important to be aware of.
  - proliferation of objects
  - *Redundant Objects*. Since relationship reifications are objects, it is possible to create multiple objects that reify the same relationship, where in other languages that permit n-ary predicates there would only be one tuple in the extension of the corresponding relation. This can be problematic when using reasoners (such as Racer [Haarslev and Möller, 2001]) that make a unique names assumption, as these multiple objects if present can be counted twice when satisfying counting axioms such as cardinality constraints.  ^t9qzkemy80rd
  - *Confusing ontology*. When classes and their instances are defined in an ontology, it is important to define what they refer to. The presence of reified relation classes and roles can create a confusion between events and fluents if one is not careful.
    - t.2024.08.07.03 yeah, but just be careful
  - *Limited use of OWL reasoning*. The use of OWL language constructs becomes severely limited with reified relationships
    - simple reasoning about inverses can have the highest impact
    - There is no a priori way todetermine which direction may be of more use to an end user.
    -  Reification prevents us from being able to express in OWL the relation inverses, ^zqsq4cdml6ud
       -  thus we are stuck with whichever direction is stated in the text
    -  Reification also prevents usage of the OWL operators transitive, symmetric, functional, and inverseFunctional on the intended relation.
   -  Local range restrictions on properties in the reified relation class must also be understood to be global restrictions on the intended relation. 
      -  To express the equivalent of local range restrictions on the intended relation, one must use nested restrictions on the role inverses
         - e.g. 
```
ObjectProperty(ManagerRel:manages
  inverseOf(ManagerRel:managedBy))
Class(Person partial
  Restriction(ManagerRel:managedBy
    allValuesFrom(
      restriction(ManagerRel:manager
        allValuesFrom(Person)))
```

  - Finally, for representing binary fluents, cardinality and value restrictions on the role inverses end up restricting the intended relation for all time
    - e.g. we cannot express in OWL that a person can have at most one manager at a time.
    - the most we can say is a person can have at most one manager
    - In most cases where such an axiom may be useful, e.g. the hasMother relation, it’s not clear the relation should be a fluent at all. 
    - At the very least, in our ontologies we could not find a use for cardinality or value restrictions on the role inverses.

#### Temporal Description Logics

-  temporal description logics reduce to a modal logic, in which times (or situations) are removed from the syntax and instead are part of the implicit quantification with only one ordering relation.
   -  we are unable to talk about what is true at any particular time in a temporal DL, we can only quantify over past and future times
   - we can not use the full Allen calculus, which is critical to our application

#### The Four-Dimensional Approach

- When two entities participate in some fluent, the fluent holds between temporal parts of those entities.

##### high-level and reusable ontology in OWL for 4D fluents

```
(Ontology 4dFluents
  (Class TimeSlice)
  (DisjointClasses TimeSlice TimeInterval)
  (Property fluentProperty Symmetric
    (domain TimeSlice)
    (range TimeSlice))
  (Property tsTimeSliceOf functional
    (domain TimeSlice)
    (range complementOf(TimeInterval)))
  (Property tsTimeInterval Functional
    (domain TimeSlice)
    (range TimeInterval)))
```

- As is often the case with high-level ontologies, there are more intended semantic constraints than can be expressed in OWL. 
  - we intend that time slices be maximal with respect to the time interval of all fluents it participates in.
    - i.e., the time interval of a time slice is defined to be the duration of the fluent holding.
    - Thus if a time slice participates in more than one fluent, they (the fluents) must hold for precisely the same interval.
      - t.2024.08.02.06 seems problematic
  - two time slices of the same entity for the same interval are equal.
- In our system, it is the responsibility of the component that transforms the output of text analysis into the knowledge-base to enforce these semantics
- The first advantage of the 4D representation is that we can use the OWL inverse operator in the expected way, as shown in the example ontology.
- Transitivity and symmetry also have the expected meaning, allowing us to express many spatial axioms in the OWL ontology:
- Cardinality restrictions can also be expressed with this approach in a way that was useful for our domain. We had several intended relations whose semantics required temporally qualified cardinality, such as “a company has at-most one CEO at a time”. 
  - does not prevent the unintended model in which a company has two overlapping time slices that have a hasCeo relation to different people
- The 4D approach is the worst among the approaches discussed here with respect to the proliferation of objects. 
  - A single fluent requires two extra objects (the time slices) and four triples.

## Conclusion

- reification of relationships further limits the use of what limited expressiveness OWL already has
- 