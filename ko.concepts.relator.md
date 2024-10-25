---
id: xbpa7vv9hwari8435fttsw3
title: Relator
desc: ''
updated: 1729850519794
created: 1721858574759
---

- aka: [[Relationship to Entity Conversion (REC)|ar.valid-time-rdf#relationship-to-entity-conversion-rec]]
- facets provide a mixin-style impressionistic
- the RDFS-style class is replaced by [[type facets|ko.concepts.facet]]
  - rdfs:Class is still used in meta ways, e.g., classifying relators
  
## Benefits

- relations can be temporalized and contextualized
- supports unary and n-ary relations
- multiple subjects can participate in relations
- 

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
:matt-groening-hasName-Matt a :NamingRelator ;
  :named-thing :matt-groening ;
  :name  "Matt" .

:matt-groening-named-Bart a :NamingRelator ;
  :name-giver  :matt-groening ;
  :named-thing :bart ;
  :name "Bart" .

:bart-isa-Simpson a :MembershipRelator ;
  :context :simpsons-world
  :member :bart ;
  :group :simpsons-family 
  .


:bart-isa-character-in-reality a :KindRelator ;
  :context :reality ;
  :individual :bart ;
  :kind :fictional-character # punning or OWL-Full
  .

:bart-isa-person-in-simpsons-world a :KindRelator ;
  :context :simpsons-world
  :individual :bart
  :kind :Person # punning or OWL-Full
  .

```

and then you can go to town with relator enhancement (temporality, attribution) etc.:

```turtle
:matt-groening-hasName-Matt a :NamingRelator ;
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
    - t.2024.10.25.02 you could have an additional property like ":subject" (which I'd been, perhaps foolishly, using generically )

## so the question becomes, generality

```turtle
:Sam-Palmisano-CEO-of-IBM a OrganizationalRoleRelator;
  :role :CEO
  :role-holder :Sam-Palmisano
  :organization :IBM
```
 