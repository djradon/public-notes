---
id: uup0x4gcs3ilsku9xbw4xcx
title: Semantic Modeling for Data
desc: ''
updated: 1716574089196
created: 1698168250108
---


- url: https://learning.oreilly.com/library/view/semantic-modeling-for/9781492054269/

## Highlights

- Based on these definitions, what do you understand to be a concept in a semantic model? Is it a set of things as the Protégé tutorial suggests, or some unit of thought as SKOS claims? And what should you do if you need to model a concept in OWL that is not really a set of things? Should you still have to make it a class? The answer, as we will see in the rest of the book, is that the SKOS definition is more accurate and useful, and that the “concept = class” claim of the OWL tutorial is at best misleading, causing several semantic modeling errors that we will see later in the book.

### Class or Individual?

; a concept can indeed play the role of a class if its definition implies a set of entities that instantiate it, but this is not always the case.
In property graphs, for example, there is no formal distinction between a class and an instance since everything is a node (node labels can play the role of a class but not exclusively
in OWL, entities that can be classes are often modeled as individuals because, otherwise, they cannot be related to other entities
Lexical variants differ from synonyms in that synonyms are different terms for the same entity, while lexical variants are different word forms for the same term.

- in OWL-DL, you cannot define a class as an instance of another class, nor can you define direct relations between classes and other entities other than some predefined ones. Thus, if you want to say at the same time that John is an instance of Data Scientist, and Data Scientist is an instance of Occupation, you just can’t.
  - ~~t.2024.04.04.13 but I think you could say that John's occupation is an instance of Data Scientist and DS is a subclass of occupation?~~
    - t.2024.05.15.08 nope
      - t.2024.05.24.11 because an individual data scientist would also be an instance of Occupation

### First Option: Model as individual and use custom relations

e.g. John is related to the individual Data Scientist via the relation hasProfession.

you can still position the entity into a hierarchy of similar entities (e.g., saying that a Data Scientist is a kind of Information Technology Professional) by using, for example, the skos:narrower relation or similar.

#### skos

- you lose reasoners (who cares?) 

### Second Option: model the concept as a class and an individual

A second workaround is to model the entity as two entities, one as a class and one as an individual, using different names for each (see approach 3 in [208]). Here are some examples of how this could happen:

    Data Scientist becomes Data Scientist (Profession) as an individual and Data Scientist (Professional) as a class

    Pneumonia becomes Pneumonia (Disease) as an individual and Pneumonia (Incident) as a class

    Eagle becomes Eagle (Species) as an individual and Eagle (Animal) as a class

    Samsung A8 becomes Samsung A8 (Mobile Phone Model) as an individual and Samsung A8 (Mobile Phone Device) as a class

The advantage of this approach is that you can state almost anything you like for your entity without caring if these statements apply only to classes or individuals. Moreover, having to name your entity in a way that makes explicit its role as a class helps avoid the naming pitfalls that we saw in Chapter 6. On the other hand, you still cannot link the two variations of the entity to each other (since one is a class and the other an individual), thus making it harder to keep them in sync with each other.

### Third Option: Punning

use OWL2 and punning, a feature that allows you to use the same entity in your model as both a class and an individual. The trick with punning is that the reasoner decides at runtime whether the entity should be interpreted as a class or individual, based on the entity’s context. Thus if, for example, the entity is linked to a class via an instantiation relation, it is treated as an individual, while if it is related to it via a subclass relation, it is treated as a class. In other words, even though the entity has one single identifier, depending on its context, it is evaluated by the reasoner as a different thing.

Keep in mind that, while punning can be a useful technique, it’s not a free ticket to treating all entities as both a class and an individual. As Michael Uschold rightly argues in [209], punning is more syntactic trickery than an actual solution to the semantic problem of metaclasses, because the only thing it does is raise an invisible wall between the two interpretations of the entity. This wall may relieve you from having to use different names for the same thing, but it can also confuse your fellow modelers and users of your model if you are not careful.


## To Subclass or Not to Subclass?

- having the different cuisines embedded within the restaurant class can make it hard to talk directly about them (e.g., you cannot easily say that one cuisine is influenced by another) or link them to other entities (e.g., with recipes). Conversely, the second model allows you to talk about cuisines but takes away from you the convenience of the subclass relation.
- The key ability that a subclass gives you in a model is that you can define relations, attributes, and other axioms that apply only to the instances of that class and not those of its superclass.