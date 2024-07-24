---
id: xbpa7vv9hwari8435fttsw3
title: Relator
desc: ''
updated: 1721863925248
created: 1721858574759
---

## How would an ontology for immutable data where relationships are primarily intermediated by relators work?

instead of 
```turtle
:matt-groening :hasName "Matt",
  :namedBy :margaret-groening
:matt-groening :named :bart
:bart a class:SimpsonsCharacter
```
we would have

```turtle
:matt-groening-named-Matt a :NamingRelation,
  :named-thing :matt-groening,
  :name  "Matt",
  :name-giver :margaret-groening,
  :when "1954-01-10"^approxInstant,
  :hadAssertionTimestamp "2024-07-24T15:25:00Z".
  :hadRetractionTimestamp 

:matt-groening-named-Bart a :NamingRelation,
  :name-giver  :matt-groening,
  :named-thing :bart,
  :name "Bart", 
  :hasCreationTime "1987Q1"^approxInstant,
  :hasValidStart "2024-07-24T15:25:00Z", 
  :hasTimestamp "2024-07-24T15:25:00Z".
```
and then you can go to town

```turtle
:mattNamedMattGroening a :NamingRelator,
  :hadNamedEntity :matt,
  :hadName  "Matt Groening",
  :hadNamingAgent :margaret
  :hadValidityStart "1954-01-10"^approxInstant,
  :hadAssertionTimestamp "2024-07-24T15:25:00Z".
  :hadRetractionTimestamp 

:mattCreatedBart a :CreationRelator,
  :hasCreator  :matt
  :hasCreatedArtifact :bart 
  :hasValidityStart "1987Q1"^approxInstant
  :hasTimestamp "2024-07-24T15:25:00Z"
```


## 