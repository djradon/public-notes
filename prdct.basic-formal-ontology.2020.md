---
id: v9zvnya3m77skyenebfzml6
title: 'BFO 2020'
desc: ''
updated: 1720710135801
created: 1715878370875
---

- https://github.com/BFO-ontology/BFO-2020/

## Features

### Temporal 

- [temporal extensions](https://github.com/BFO-ontology/BFO-2020/blob/master/src/owl/profiles/temporal%20extensions/README.md)
  - To satisfy needs of the community then, the BFO development team encourages a strategy of developing and deploying Temporal Extensions which will provide users options for representing time in their domains.
  - Given the need to represent time and change in many domains and the wide use of OWL in ontology circles, proposals have been offered by users of BFO for representing such phenomena within the binary constraints of OWL. Examples include:

    -   [Temporalized Relations](https://github.com/BFO-ontology/BFO-2020/blob/master/src/owl/profiles/temporal%20extensions/temporalized%20relations/owl/README.md)  
        -   https://github.com/BFO-ontology/BFO-2020/blob/master/src/owl/profiles/temporal%20extensions/temporalized%20relations/owl/bfo-temporalized-relations.ttl
    -   [Temporal Interpretation Annotation](https://oborel.github.io/obo-relations/temporal-semantics/)

#### Competency Questions for temporal representation

- https://github.com/CommonCoreOntology/CommonCoreOntologies/issues/118

##### How to turn dates into into temporal information

- https://github.com/CommonCoreOntology/CommonCoreOntologies/issues/118#issuecomment-810285200
- Purposes:
  - reasoning and inferencing; when rules can't be express in (OWL?) DL, use [[prdct.spin]]
  - sparql queries for now or historical
  - recording provenance. "text in a document that denotes a day, month, or year is typically as close as I can get to knowing the temporal region during which a process occurs."
  - assumption: "The temporal region does not explicitly state the starting and ending moments, but these values can be calculated."
  - I assert the process to be the subject of an [[t.km.ontology.information-content-entity]], which in turn generically depends on an [[t.km.ontology.information-bearing-entity]]. The Information Bearing Entity is the subject of a triple in the above form, where the predicate is cco:has_date_value and the object is a literal, either with a language tag or of type xsd:string.
  - I create a temporal interval based on the text literal. I associate the temporal interval with the process and the Information Content Entity.
```
:process occupies-temporal-region :tr .
:tr designated-by :ice .
:ice generically-depends-on-at-all-times :ibe .
:ibe has-date-value "March 31"@en .
```
This establishes provenance. Next I create temporal instants representing the first and last instants of March 31:
```
:instant-01 a cco:TemporalInstant .
:instant-02 a cco:TemporalInstant .
:tr has-first-instant :instant-01 .
:tr has-last-instant :instant-02 .
```