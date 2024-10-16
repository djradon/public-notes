---
id: xbpa7vv9hwari8435fttsw3
title: Relator
desc: ''
updated: 1728319563785
created: 1721858574759
---

- the RDFS-style class might have to be sidelined
  - t.2024.08.09.20 what? more like traditional "relationship directly expressed with predicate" gets replaced by "RelationshipClass has shapes, pieced together impressionistic style from meta-predicates"


## What would it look like to have a "domain-classes-as-individuals" data model where relationships are primarily expressed by relators?

instead of 

```turtle
:mattGroening :hasName "Matt" .
:mattGroening :gaveName :bart .
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
  :context :simpsons-world
  :member :bart ;
  :group :simpsons-family ;
  :groupClass :SimpsonsFamily, foaf:Person. //kinda redundant, but that's OK


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
  :hadAssertionTimestamp "2024-07-24T15:25:00Z" .
```


## Thoughts

- is that just making relations into "assertions? Which are kinda events?
- sure, a profusion of predicates, but it's still legible. As long as we have tools for creation, a profusion of predicates is okay

## Benefits

- can clarify the type/is-a relationships between individuals and classes
  - i.e.,
    - membership?
    - kind?
    - role?

## Issues

### Relator Naming

- you could rename the relators without change the underlying "data"... e.g., if Sam Palmisano was CEO of IBM again, you could rename the original :Sam-Palmisano-CEO-of-IBM to :Sam-Palmisano-CEO-of-IBM-1 or :Sam-Palmisano-CEO-of-IBM-2002
  - if you're going for immutability, do you need a new relator IRI as soon as the data changes? I guess so, but even if you're just adding predicate-object pairs to the same relator? 
    - gets into aliasing? 
    - gets into transactions... want to add all the roles and metadata at once.
    - a "record" isn't really immutable if you add invalidation and successor metadata
    - relevant to [[prdct.RDF-star]]: you should be able to annotate a set up triples. or treat a set of triples as a unit. maybe named-graph per relator?
  - being 

### Inversion

![[ar.a-reusable-ontology-for-fluelnts-in-owl#^zqsq4cdml6ud]]
- I thought I saw somewhere that there would just be a profusions of inverse properties, but maybe it's actually impossible.
- it seems like inversion might not be appliable to relator-based RDF. and that's probably okay. Who cares about ceoOf vs hasCEO when you have a ceo role and a company role on the same footing
  - t.2024.10.07.09 for meaning, it obviates the need to distinguish between active and passive voices, although you might want to preserve that distinction for reasons of accuracy. I guess there might be small variations in meaning

## so the question becomes, generality

```turtle
:Sam-Palmisano-CEO-of-IBM a OrganizationalRoleRelation;
  :role :CEO
  :role-holder :Sam-Palmisano
  :organization :IBM
```
 