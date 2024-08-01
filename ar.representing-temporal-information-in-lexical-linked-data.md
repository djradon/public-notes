---
id: m3s2x1ajzacl8o0sfts1fcd
title: Representing Temporal Information in Lexical Linked Data
desc: ''
updated: 1722506252923
created: 1722150870542
---

- https://aclanthology.org/2020.ldl-1.3.pdf
- author: @anas-fahad-khan

## Introduction

- The difficulties of representing relationships that change with time – also referred to as fluents or diachronic rela- tions in the literature – in RDF have been by now well- rehearsed ( @christopher-welty et al., 2006)

##  Temporal Information in Lexical Datasets

- in previous related work we have looked at how to represent etymologies, viewed as hypotheses about word histories, explictly both in RDF (Khan, 2018) and in the Lexical Markup Framework (Khan and Bowers, 2020).
- temporal information is not always explicitly included in the form of an etymology.
- common for resources to list the senses in each lexical entry in some order of temporal precedence
- Other resources in- clude descriptions of the semantic shift processes which led from temporally antecedent senses to subsequent senses;
- others mark senses (or forms, etc) as obsolete and/or give some basic information on the time period in which a sense or form (or grammatical construct) was in use or was most commonly in use
  - in fact, in these and in other contexts, one frequently finds reference to a particular historical stage of a language, such as Old French or Middle English, something which also helps to group together lexical phenomena in time.

## "Our approach"

- firstly, we propose the use of qualitative intervals to model temporal vagueness in lexical data;
-  secondly, we define a ‘perdurantist’ version of certain classes in the ontolex-lemon model in order to allow lexical entries, senses, etc, to each have a ‘lifespan’ as well as temporal parts.
-  there already exists a set of SWRL rules which allow for reasoning over data that describes intervals qualitatively using these relations (Batsakis et al., 2017)
-  

## Perdurantism v. Endurantism

topics: [[t.phil.perdurantism]] [[t.phil.endurantism]]

- Perdurantism by treating people, animals, and things in general like processes, only parts of which exist at different times, has the clear shortcoming that it can be unintuitive and difficult to understand.
  - countierintuitive
  - helps to resolve a number of longstanding metaphysical conundrums relating to change over time.
  - provides a very useful way of modelling vagueness
  - able to meet several of the challenges raised against more traditional the- ories of time and change by the theory of special relativity (Effingham, 2012)
- Note that although the names ‘three- dimensionalism’ and ‘four-dimensionalism’ might suggest that we are only dealing with ‘concrete’ objects, namely those that occupy a continuous physical portion of space, this is not in fact the case and perdurantism has in fact been applied to musical works (Caplan and Matheson, 2006) and institutional objects (Hansson Wahlberg, 2014)
- Our proposal in this work is to apply it to language and linguistic phenomena.

### non-liguistic Example: capitalCity of Italy

- Turin from 1861 to 1865 (period t1), Florence from 1865 to 1871 (the period t2), and Rome from 1871 to the current day (the interval t3).
- We define separate time slices (or temporal parts) TurinCapital, FlorenceCapital, RomeCapital of each of the Italian cities mentioned above, Turin, Florence, Rome respectively. Note that each of these time slices are also typed as cities, e.g., city(Turin) and city(TurinCapital)
- We relate the temporal parts of these cities to- gether with their wholes using the property tem- poralPartOfwhich relates a perdurant together with another perdurant of which it is a temporal part, i.e., temporalPartOf(TurinCapital, Turin), temporalPartOf(FlorenceCapital, Florence), and temporalPartOf(RomeCapital, Rome)
- Each of these timeslices is associated with its lifespan using the temporalExtent property which relates a perdurant together with the interval during which it exists, i.e., temporalExtent(TurinCapital, t1), temporalExtent(FlorenceCapital, t2), temporalExtent(RomeCapital, t3).
- We also create time slices of Italy for each of these periods, Italyt1,Italyt2 and Italyt3 where: temporalExtent(Italyt1,t1),temporalExtent(Italyt2,t2), and temporalExtent(Italyt3,t3)
- Finally we relate these timeslices of Italy using the capitalCity relation: capitalCity(TurinCapital,Italyt1), capitalCity(FlorenceCapital,Italyt2), capitalCity(RomeCapital,Italyt3)
- This is a version of the kind of perdurantist approach initially proposed for RDF in (Welty et al., 2006);
  - ? [[ar.a-reusable-ontology-for-fluents-in-owl]]
  - our version is more directly based on (Krieger, 2014) [[ar.detailed-comparison-of-seven-approaches-for-the-annotation-of-time-dependent-factual-knowledge-in-rdf-and-owl]]
  - HOWEVER, when it comes to creating diachronic versions of relationships between a lexical entry and its lexical senses and forms we can make a simplification: since the lifespan of a sense/form is necessarily contained in the lifespan of an entry, when it comes to perdurants versions of these classes, to define sense as holding between lexical entries and senses (and form as holding between lexical en- tries and forms) rather than timeslice of these, as in the case of capitalCity.

### First Defintions

- perdurantist sub-classes of the ontolex-lemon classes Lexical Entry, Lexical Sense, and Lexical Form; these are pLexical Entry, pLexical Sense, and pLexical Form
- In order to define these classes we will make use of the new object property mentioned above, temporalExtent, whose range is the owl-time class time:Interval, and whose purpose is to relate a perdurant to its temporal dimension
  - thereafter we impose the restriction that each member of the p-classes is related to exactly one time:Interval individual via the property temporalExtent

### Girl

- we start by defining the entry as a pLexicalEntry with an associated temporal extent (girl_time) and relating the entry with its forms using the (non-fluent) ontolex-lemon property lexicalForm

```turtle
:girl rdf:type :pLexicalEntry ;
  :temporalExtent :girl_time;
  ontolex:lexicalForm :garl_form ,
    :garle_form ,
    :geerl_form , ... .
```
- The first two forms which we will look at from the list given in Listing 7 are garl and girle, the first of which the OED tells us was in use during the Middle English period and the second of which was in use from the Middle English period through to the 15th century.
- after we introduce them as elements of type pForm we thereafter associate them with a given temporal interval using the property temporalExtent. 
```turtle
:garl_form rdf:type :pForm ;
  ontolex:writtenRep "garl";
  :temporalExtent :enm_interval .

:girle_form rdf:type :pForm ;
  ontolex:writtenRep "girle";
  :temporalExtent :ME-16 .
```

- we have added a new datatype property hasUsageNote to our model; this allows for the encoding of geographical and dialectal constraints on the usage of a lexical element as free text.
- we model the temporal interval associated with gurl_form as consisting of two separate temporal part: relating it to the interval enm_interval using interval- StartedBy and the interval 18- using intervalFinishedBy

```turtle
gurl_form a :pForm ;
  :hasTemporalPart :gurl_form_IEN , :gurl_form_ME ;
  :temporalExtent [
    a owl-time:Interval;
    owl-time:intervalStartedBy :enm_interval;
    owl-time:intervalFinishedBy :18-;
  ];
ontolex:writtenRep "gurl"@en .

:gurl_form_ME a :pForm ;
  :temporalExtent :enm_interval .

:gurl_form_IEN a :pForm ;
  :temporalExtent :18- ;
  :hasUsageNote
    "chiefly Irish English and nonstandard"@en .
```

- the entry for this sense also identifies a temporal part of this sense with a particular quality not shared by the whole: that of being limited to a certain geographically defined dialect (Irish English, or more precisely the dialect of Wexford)

```turtle
:girl ontolex:sense :sense_I1 ,
    :sense_I1_irish_english .

:sense_I1 a :pLexicalSense ;
  :hasTemporalPart :sense_I1_irish_english ;
  :temporalExtent :sense_I1_interval .

:sense_I1_irish_english :pLexicalSense ;
  :temporalExtent :sense_I1_irish_english_interval ;
: hasUsageNote "Irish English (Wexford)"@en .
```

- then we use the temporal examples to enrich the representation of each sense

```turtle
:sense_I1_interval a owl-time:Interval ;
  owl-time:hasEnd :present ;
  owl-time:intervalFinishedBy

:sense_I1_irish_english_interval;
  owl-time:intervalContains
    :a1475 , :circa_1300 , :year_1996 .

:sense_I1_irish_english_interval a owl-time:Interval;
  owl-time:intervalFinishes :sense_I1_interval ;
  owl-time:intervalContains :a1827 .
```