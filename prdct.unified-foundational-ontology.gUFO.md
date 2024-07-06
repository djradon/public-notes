---
id: c3cf5t7ybox6k56n992pnkr
title: gUFO
desc: 'gentle unified foundational ontology'
updated: 1720276068482
created: 1720274927117
---

- https://nemo-ufes.github.io/gufo/
- similar: [[prdct.unified-foundational-ontology.eUFO]]

## Issues

- not OWL-DL

## Features

- Treating aspects as endurants (i.e., reifying aspects) allows us to consider the properties of aspects themselves, and track their change in time.
- temporal aspects of concrete individuals can be captured with the data properties gufo:hasBeginPointInXSDDate, gufo:hasBeginPointInXSDDateTimeStamp, gufo:hasEndPointInXSDDate and gufo:hasEndPointInXSDDateTimeStamp

- A key feature of UFO (and hence, gUFO) is that it includes two taxonomies: one with classes whose instances are individuals (classes in this taxonomy include gufo:Object, gufo:Event) and another with classes whose instances are types (classes in this taxonomy include gufo:Kind, gufo:Phase, gufo:Category). ^io6179ll2dle

### Taxonomy

-   Individual
    -   AbstractIndividual
    -   ConcreteIndividual
        -   Endurant
            -   Object
            -   Aspect
        -   Event
        -   Situation
-   Type
    -   AbstractIndividualType
    -   ConcreteIndividualType
        -   EndurantType
            -   Sortal
                -   Kind
                -   Phase
                -   Role
                -   SubKind
            -   NonSortal
                -   Category
                -   PhaseMixin
                -   RoleMixin
                -   Mixin
        -   EventType
        -   SituationType
    -   RelationshipType