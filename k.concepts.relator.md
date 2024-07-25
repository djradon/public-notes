---
id: xbpa7vv9hwari8435fttsw3
title: Relator
desc: ''
updated: 1721944605252
created: 1721858574759
---

- the RDFS concept of class might have be sidelined

## How would an ontology for immutable data where relationships are primarily intermediated by relators work?

instead of 
```turtle
:matt-groening :hasName "Matt" .
:matt-groening :named :bart .
:bart a class:SimpsonsCharacter .
```
we would have

```turtle
:matt-groening-hasName-Matt a :NamingRelation ;
  :named-thing :matt-groening ;
  :name  "Matt" .

:matt-groening-named-Bart a :NamingRelation ;
  :name-giver  :matt-groening ;
  :named-thing :bart ;
  :name "Bart" .

:bart-a-Simpson a :MembershipRelation ;
  :member :bart ;
  :group :simpsons-characters .
```
and then you can go to town with event enhancement, temporality, etc.:

```turtle
:matt-groening-named-Matt a :NamingRelation ;
  :named-thing :matt-groening ;
  :name  "Matt" ;
  :name-giver :margaret-groening ;
  :when "1954-01-10"^approxInstant ;
  :hadAssertionTimestamp "2024-07-24T15:25:00Z" ;
  :hadRetractionTimestamp .

```


## 