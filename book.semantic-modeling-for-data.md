---
id: uup0x4gcs3ilsku9xbw4xcx
title: Semantic Modeling for Data
desc: ''
updated: 1721150412690
created: 1698168250108
---


- url: https://learning.oreilly.com/library/view/semantic-modeling-for/9781492054269/

## Highlights

- Based on these definitions, what do you understand to be a concept in a semantic model? Is it a set of things as the Protégé tutorial suggests, or some unit of thought as SKOS claims? And what should you do if you need to model a concept in OWL that is not really a set of things? Should you still have to make it a class? The answer, as we will see in the rest of the book, is that the SKOS definition is more accurate and useful, and that the “concept = class” claim of the OWL tutorial is at best misleading, causing several semantic modeling errors that we will see later in the book.

### Class or Individual?

; a concept can indeed play the role of a class if its definition implies a set of entities that instantiate it, but this is not always the case. In property graphs, for example, there is no formal distinction between a class and an instance since everything is a node (node labels can play the role of a class but not exclusively in OWL, entities that can be classes are often modeled as individuals because, otherwise, they cannot be related to other entities

- in [[prdct.owl.dl]], you cannot define a class as an instance of another class, nor can you define direct relations between classes and other entities other than some predefined ones. Thus, if you want to say at the same time that John is an instance of Data Scientist, and Data Scientist is an instance of Occupation, you just can’t.
  - ~~t.2024.04.04.13 but I think you could say that John's occupation is an instance of Data Scientist and DS is a subclass of occupation?~~
    - t.2024.05.15.08 nope
      - ~~t.2024.05.24.11 because an individual data scientist would also be an instance of Occupation~~
    - t.2024.07.14.15 I think I was confusing specialization with instantiation, see [[prdct.unified-foundational-ontology.gUFO#usage-scenarios]]

### First Option: Model as individual and use custom relations

e.g. John is related to the individual Data Scientist via the relation hasProfession.

- you can still position the entity into a hierarchy of similar entities (e.g., saying that a Data Scientist is a kind of Information Technology Professional) by using, for example, the skos:narrower relation or similar.
- you get the freedom to use the entity in any relations you like, not only instantiation, keeping at the same time its instances in short reach.
- 

#### skos

- you lose some reasoning (how much?) 

### Second Option: model the concept as a class and an individual

A second workaround is to model the entity as two entities, one as a class and one as an individual, using different names for each (see approach 3 in [208]). Here are some examples of how this could happen:

    Data Scientist becomes Data Scientist (Profession) as an individual and Data Scientist (Professional) as a class

    Pneumonia becomes Pneumonia (Disease) as an individual and Pneumonia (Incident) as a class

    Eagle becomes Eagle (Species) as an individual and Eagle (Animal) as a class

    Samsung A8 becomes Samsung A8 (Mobile Phone Model) as an individual and Samsung A8 (Mobile Phone Device) as a class

The advantage of this approach is that you can state almost anything you like for your entity without caring if these statements apply only to classes or individuals. Moreover, having to name your entity in a way that makes explicit its role as a class helps avoid the naming pitfalls that we saw in Chapter 6. 

On the other hand, you still cannot link the two variations of the entity to each other (since one is a class and the other an individual), thus making it harder to keep them in sync with each other.

- t.2024.06.08.21 but you can use annotations to link them

### Third Option: Punning

use OWL2 and punning, a feature that allows you to use the same entity in your model as both a class and an individual. The trick with punning is that the reasoner decides at runtime whether the entity should be interpreted as a class or individual, based on the entity’s context. Thus if, for example, the entity is linked to a class via an instantiation relation, it is treated as an individual, while if it is related to it via a subclass relation, it is treated as a class. In other words, even though the entity has one single identifier, depending on its context, it is evaluated by the reasoner as a different thing.

Keep in mind that, while punning can be a useful technique, it’s not a free ticket to treating all entities as both a class and an individual. As @michael-uschold rightly argues in [209], punning is more syntactic trickery than an actual solution to the semantic problem of metaclasses, because the only thing it does is raise an invisible wall between the two interpretations of the entity. This wall may relieve you from having to use different names for the same thing, but it can also confuse your fellow modelers and users of your model if you are not careful.


## To Subclass or Not to Subclass?

- having the different cuisines embedded within the restaurant class can make it hard to talk directly about them (e.g., you cannot easily say that one cuisine is influenced by another) or link them to other entities (e.g., with recipes). Conversely, the second model allows you to talk about cuisines but takes away from you the convenience of the subclass relation.
- The key ability that a subclass gives you in a model is that you can define relations, attributes, and other axioms that apply only to the instances of that class and not those of its superclass.
- low rigidity subclasses require more maintenance

### Things to Remember

- Useful subclasses are those that have additional attributes, relations, or other characteristics compared to their parent class, and these characteristics are commonly used in the domain of discourse
- Avoid subclasses with low rigidity as they are harder to maintain



## Fuzzification

- we can assign a real number to a vague statement, within a range from 0 to 1. A value of 1 would mean that the statement is completely true, a value of 0 means that it is completely false, and any value in between that is “partly true” to a given, quantifiable extent.
- fuzzy truth degrees are not probabilities
  - A probability statement is about quantifying the likelihood of events or facts whose truth conditions are well defined to come true (e.g., “it will rain tomorrow with a probability of 0.8”), while a fuzzy statement is about quantifying the extent to which events or facts whose truth conditions are undefined can be perceived as true.
- Truth fuzzification makes sense only when it manages to reduce disagreements over the validity of a model’s vague statements, and the benefits of this reduction outweigh the fuzzification effort and cost
- t.2024.07.16.10 instead of assigning numeric truth values
  - for class membership restrictions and you could do "always, sometimes, sometimes/usually, sometimes/often, sometimes/occasionally, sometimes/rarely, never" and also perhaps "periodically, sporadically"

### Fuzzification Options

- The number and kind of fuzzy degrees you need to acquire for your model’s vague elements depend on the latter’s vagueness type and dimensions.
- Commonly used fuzzy membership functions: (a) trapezoidal function, (b) triangular function, (c) left-shoulder function, (d) right-shoulder function, and (e) linear function
- if an element has quantitative vagueness in more than one dimension, then things become a bit more complicated. 
  - One option is to define a multivariate fuzzy membership function like the one in Figure 12-5, i.e., a function with one variable for each dimension. For example, if you have the class CompetitorCompany that you have identified as quantitatively vague in the dimensions of revenue and employee count, then you could define a two-variable function based on these dimensions.
  - Another option is to define one membership function per dimension and then combine these via some fuzzy logic operation, like fuzzy conjunction or fuzzy disjunction