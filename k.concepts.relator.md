---
id: xbpa7vv9hwari8435fttsw3
title: Relator
desc: ''
updated: 1721949191030
created: 1721858574759
---

- the RDFS concept of class might have be sidelined

## What would it look like to have a "domain-classes-as-individuals" ontology for immutable data where relationships are primarily expressed by relators?

instead of 

```turtle
:mattGroening :hasName "Matt" .
:mattGroening :named :bart .
:bart :hasName "Bart" .
:bart a :FictionalCharacter .
:bart a :Person .
:bart a :SimpsonFamily
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

:bart-isa-Simpson a :MembershipRelation ;
  :member :bart ;
  :group :simpsons-family .

:bart-isa-character-in-reality a :KindRelation ;
  :context :reality ;
  :individual :bart ;
  :kind :fictional-character .

:bart-isa-person-in-simpsons-world a :KindRelation ;
  :context :simpsons-world
  :individual :bart
  :kind :person

```

and then you can go to town with relator enhancement (temporality, attribution) etc.:

```turtle
:matt-groening-hasName-Matt a :NamingRelation ;
  :named-thing :matt-groening ;
  :name  "Matt" ;
  :name-giver :margaret-groening ;
  :name-giver :homer-groening ;
  :when "1954-01-10"^approxInstant ;
  :hadAssertionTimestamp "2024-07-24T15:25:00Z" ;
  :hadRetractionTimestamp .

```


## Thoughts

- is that just making relations into "assertions? Which are kinda events?

## Benefits

- can clarify the type/is-a relationships between individuals and classes
  - i.e.,
    - membership?
    - kind?
    - role?