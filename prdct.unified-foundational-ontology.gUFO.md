---
id: c3cf5t7ybox6k56n992pnkr
title: gUFO
desc: gentle unified foundational ontology
updated: 1728704240112
created: 1720274927117
---

- https://nemo-ufes.github.io/gufo/
- similar: [[prdct.unified-foundational-ontology.eUFO]]

## Issues

- not OWL-DL because powerclasses? (punning)
- doesn't support [[t.km.ontology.multi-level-theory]], see [[community.nemo-ufes.gufo.issues-37-multi-level]] 
- abstract and concrete are disjoint, but e.g. wemi... things are a blend

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

### Usage Scenarios

Considering these two taxonomies, the following usage scenarios are envisioned and discussed in this document where appropriate:

1.  A UFO-based ontology _instantiates_ gUFO classes in the taxonomy of individuals  
    For example, `:Earth rdf:type gufo:Object` and `:WorldCup1970Final rdf:type gufo:Event`.
2.  A UFO-based ontology _specializes_ gUFO classes in the taxonomy of individuals  
    For example, `:Planet rdfs:subClassOf gufo:Object` and `:SoccerMatch rdfs:subClassOf gufo:Event`.
3.  A UFO-based ontology _instantiates_ gUFO classes in the taxonomy of types  
    For example, `:Planet rdf:type gufo:Kind`, `:Child rdf:type gufo:Phase`.
4.  A UFO-based ontology _specializes_ gUFO classes in the taxonomy of types  
    For example, `:PersonPhase rdfs:subClassOf gufo:Phase`.

Users may combine the various scenarios discussed. For example, users will often employ scenarios 2 and 3 in combination as shown in the following fragment, which defines a "Person" class that specializes gufo:Object and instantiates gufo:Kind:

```turtle
:Person rdf:type owl:Class ;
        rdfs:subClassOf gufo:Object ;
        rdf:type gufo:Kind .
```

## Questions

- "Every gufo:Endurant instantiates one and only one gufo:Kind" - so no flying cars?
  - @chatgpt: define a new kind, or use a generalization

## Resources

- [[ar.ontology-implementation-with-g-ufo-a-hands-on-tutorial]]
- 