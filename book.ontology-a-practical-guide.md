---
id: 0voi8xiinkfuqhpm646ndb7
title: Ontology a Practical Guide
desc: ''
updated: 1718136653001
created: 1709663700412
---

- author: @adam-pease

## Chapter 2

- concerned with knowledge representation languages that allow for deduction. 
  - schema are low-expressivity and low-formality, e.g. relational database, XML
  - taxonomy are in the middle, e.g. RDF/S, UML, OWL
  - Logical Theory are high, e.g. [[prdct.knowledge-interchange-format]] and [[prdct.tptp]] are the most expressive and most formal
- "every software system has an ontology", it maybe just isn't made explicit
- "semantic networks" is one of the earliest [[t.km.knowledge-representation]]
- [[t.cs.object-orientation]] combine procedural specification with a small amount of declarative (e.g., classes, instances, class-subclass relations), i.e., the barest minimum
- Frame languages lack a facility for expressing rules
- [[t.km.description-logic]]

### [[t.phil.logic.first-order-logic]] in [[prdct.suo-kif]]

- no embedded formulas/propositions (only in higher-order logics)

### Ontology Development Pitfalls

- Confusing Instance and Subclass
- Part-of vs. Subclass
- 

### Modeling Events as Relations

- don't do (eats Bill HamSandwich); 
  - presumably, model events as things unto themselves
- "Davisonian event representation" looks a lot like what I was planning to do with hypergraphs
- most languages that have some use in inference, like OWL, don't allow statements as arguments to relations, because it's extremely difficult to reason with.


#### Example

```json
{
  "@id": "ex:Brutus-stabbed-Caesar",
  "@type": "ont.occurence.
}
```
- another reason to do kebab or snake case... preservation of capitalization (if you wanna go that route)

### Ontological Promiscuity / Confusing Language and Concepts

- terms need to be well-defined

### Modelling Roles as Classes

- yay, typedb

### Modal vs Normative

- can, may, should != obliged to, allowed to

### Chapter 2 Exercises

#### An elephant is a mammal

(forall (?X)
  (=>
    (instance ?X Elephant)
    (instance ?X Mammal)))

#### Bob Likes Sue

(likes Bob Sue)

####  Koko is a gorilla

(instance Koko Gorilla)

#### Every farmer like a horse

(forall (?X)
  (=>
    (instance ?X Farmer)
    (exists (?Y)
      (and 
        (likes ?X ?Y)
        (instance ?Y Horse)))))


## Chapter 3: Ontologies (in the broadest sense)

- DOLCE universals are only employed in the service of describing particulars
- SUMO is an ontology of both particulars and universals
  - SUMO has a hierarchy of properties as well as classes ^79dmzjqovfhx