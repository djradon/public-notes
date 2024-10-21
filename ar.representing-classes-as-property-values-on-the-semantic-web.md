---
id: 7gdjffs2qd4lj0b7v7ei4vf
title: Representing Classes as Property Values on the Semantic Web
desc: ''
updated: 1729507918351
created: 1729505642229
---

- https://www.w3.org/TR/swbp-classes-as-values/
- authors: @natasha-noy @michael-uschold @christopher-welty
- topics: [[t.km.ontology.multi-level-theory]] [[t.cs.semantic-web.class.class-as-values]]

## Abstract

This document addresses the issue of using classes as property values in OWL and RDF Schema. It is often convenient to put a class (e.g., Animal) as a property value (e.g., topic or book subject) when building an ontology. While OWL Full and RDF Schema do not put any restriction on using classes as property values, in OWL DL and OWL Lite most properties cannot have classes as their values. We illustrate the direct approach for representing classes as property values in OWL-Full and RDF Schema. We present various alternative mechanisms for representing the required information in OWL DL and OWL Lite. For each approach, we discuss various considerations that the users should keep in mind when choosing the best approach for their purposes.

## Highlights

### Approach 1: Use classes directly as property values

- The resulting ontology is compatible with RDF Schema and OWL Full, but it is outside OWL DL and OWL Lite.
- This approach is probably the most succinct and intuitive among all the approaches proposed here.
- Applications using this representation can directly access the information needed to infer that Lion (the subject of the LionsLifeInThePrideBook individual) is a subclass of Animal and that AfricanLion (the subject of the TheAfricanLionBook individual) is a subclass of Lion.
- If we need to restrict the range of values for the dc:subject property, then we need to create an additional class for such a restriction. For instance, we may want to define a class of all books about animals—BookAboutAnimals—that our animal books will be instances of and we want to restrict the range of values for the dc:subject property for the BookAboutAnimals class to the class Animal and its subclasses. One way to define such restriction is as follows:

```turtle
:BookAboutAnimals
      a       owl:Class ;
      rdfs:subClassOf :Book ;
      rdfs:subClassOf
              [ a       owl:Class ;
                owl:unionOf ([ a       owl:Restriction ;
                               owl:onProperty dc:subject ;
                               owl:hasValue Animal
                             ] 
                             [ a       owl:Restriction ;
                               owl:onProperty dc:subject ;
                               owl:someValuesFrom
                                    [ a       owl:Restriction ;
                                      owl:onProperty rdfs:subClassOf;
                                      owl:hasValue Animal 
                                    ]
                          ])
              ] .
```

Summary: this approach is a good one to use if you care about simplicity, do not have to be in OWL DL, and either do not need to limit the range of the dc:subject values or do not care that you also need to use classes as subjects to implement this restriction.

### Approach 2: Create special instances of the class to be used as property values

We can treat the hierarchy of animal species as a hierarchy of subjects, create individuals corresponding to all the subjects and use these individuals as values for the dc:subject property (Figure 2).

- The resulting ontology is compatible with RDF Schema and OWL Lite (and hence OWL DL)
- The class Lion has an instance that is the subject lion. Creating an instance of the Lion class to represent a specific lion at the zoo would be inconsistent with this interpretation. Therefore, we will need to have a different class to represent  lions at the zoo. This change has important implications if the hierarchy of animals is not created by us, but we imported it from somewhere else. Applications will interpret the reference to imported classes according to their original definitions. Other ontologies importing the same hierarchy of animals will in fact use the original definition. Therefore, there may be inconsistency not only in our own interpretation but also when our ontology is integrated with others importing the same resource. This consideration is not a problem when interoperability is not an issue.
- In this approach, there is no explicit direct relation (i.e., a relation that a general-purpose reasoner can readily identify) between the LionSubject individual defined above and, for example, an AfricanLionSubject individual, which is an instance of AfricanLion... An application trying to utilize this relation (for example, to extract books about African lions when asked for books about lions), will need to be aware of this specific approach and know to trace back to the corresponding classes, their subclasses, and respective instances. A general-purpose reasoner will not be able to use this information directly. Note however that the individual AfricanLionSubject is also an instance of the Lion class. Therefore, if we ask for all books where dc:subject is an instance of the Lion class we will get the books that are annotated with AfricanLionSubject.
- There is a maintenance penalty: We need to maintain a set of instances for all subjects in addition to the hierarchy of subjects and ensure that the two sets—classes representing subjects and corresponding individuals—are consistent with each other (e.g., that they have the same names, etc.). However, developers can instrument tools that would maintain this consistency automatically.
- Some may consider this approach to be "too messy" for the simple task at hand
- Defining a range restriction for the dc:subject property for the class BookAboutAnimals is straightforward.

![](/assets/images/2024-10-21-03-31-41.png)

### Approach 3: Create a parallel hierarchy of instances as property values

![](/assets/images/2024-10-21-03-32-10.png)

- The resulting ontology is compatible with RDF Schema and OWL Lite (and hence OWL DL). However, note that RDF Schema does not have transitive properties, thus we will not be able to express the transitivity of the parentSubject property in RDF Schema.
- Most DL reasoners will be able to infer transitive relations between subjects, such as the fact that AnimalSubject is a parentSubject of AfricanLionSubject. However, a DL reasoner will not be able to infer that a book that has LionSubject as the value for dc:subject is also about Animals. More specialized reasoners may be able to infer this information.
- The resulting hierarchy of subjects is not related to or dependent on the class hierarchy representing the same topics (in this case, animals), except through an annotation property rdfs:seeAlso. Annotation properties however, are usually ignored by inference engines.
- Some may consider the approach of having two parallel hierarchies representing essentially the same information to be too complicated and difficult to maintain for the simple task at hand
- This approach explicitly separates the subject terminology from the corresponding ontology. Many consider this separation a good modeling practice: the semantics of a subject Lion can be different from the semantics of the class of lions. Having subjects in a separate hierarchy, would allow us to define for example that the subject Africa is a parent subject of the subject AfricanLion.
- The separation of the subject terminology from the corresponding ontology incurs a serious maintenance penalty: We need to maintain a set of instances for all subjects in addition to the hierarchy of subjects. In many applications, we may also need to ensure that the two sets—classes representing subjects and corresponding individuals and values for the parentSubject property—are consistent with each other. However, developers can instrument tools that would maintain this consistency automatically.
- Defining a range restriction for the dc:subject property for the class BookAboutAnimals is straightforward

Summary: This approach may be a good one to use if staying within OWL DL is important. It also allows you to use a DL reasoner to infer transitive relationships between subjects. It does carry the penalty of having two parallel "hierarchies."

### Approach 4: Create a special restriction in lieu of using a specific value

This approach enables us to use a DL reasoner to infer, for example, that a book that has Lion as a subject also has Animal as its subject. In this approach, we create a new class to represent a class of all books with a particular subject. For example, we create a class BookAboutLions to represent all books that have Lion as one of their subjects. We then assign a subject to a specific book by making the book an instance of one of these classes, instead of explicitly setting a property value for the instance. Thus, for example the individual LionsLifeInThePrideBook will be an instance of the class BookAboutLions (Figure 4). We create similar classes for any subject category of books that we are interested in, such as BookAboutAnimals, BookAboutAfricanLions .

![](/assets/images/2024-10-21-03-36-31.png)

This approach _approximates_ the interpretation that we used in the previous approaches by using unspecified members of a class rather than the class itself as property values.

A DL reasoner will be able to classify LionsLifeInThePrideBook as an instance of the class BookAboutAnimals.

Note that there a correspondence between the hierarchy of classes of books on specific subjects (such as BookAboutAnimals, BookAboutLions, and BookAboutAfricanLions) and the classes in the species hierarchy that we use as subjects (Animal, Lion, AfricanLion). The hierarchy of books essentially parallels the hierarchy of subjects, although it does not have to have a book class corresponding to each subjects—only the subjects that we are interested in. If the book classes are defined as above, a DL reasoner will be able to infer automatically the hierarchy of book classes, based on the hierarchy of subjects.

A DL reasoner will be able to classify LionsLifeInThePrideBook as an instance of the class BookAboutAnimals.

Note that there a correspondence between the hierarchy of classes of books on specific subjects (such as BookAboutAnimals, BookAboutLions, and BookAboutAfricanLions) and the classes in the species hierarchy that we use as subjects (Animal, Lion, AfricanLion). The hierarchy of books essentially parallels the hierarchy of subjects, although it does not have to have a book class corresponding to each subjects—only the subjects that we are interested in. If the book classes are defined as above, a DL reasoner will be able to infer automatically the hierarchy of book classes, based on the hierarchy of subjects.

There is a variant to this approach in which we merge the two steps into one. Instead of creating an explicit named class, BookAboutLions, and then creating an instance of this class, we create the instance and assign its type to be an anonymous class of type owl:Restriction. In this variant, there is no explicitly named class corresponding to BookAboutLions

#### Considerations for approach 4

- 
- The resulting ontology is compatible with OWL DL. Since this approach uses restrictions, which do not have any semantics in RDF Schema, we cannot use this approach for RDF Schema.
- The interpretation of this pattern is different from interpretations of the other patterns in this note: the subject of the book is one or more specific lions—individuals in the Lion class—rather than the Lion class itself . In this case, a book about lions is a book about some lions, even if that happens to be all lions.
- A Description Logic reasoner will be able to classify automatically the individual LionsLifeInThePrideBook that has an instance of a Lion class as its subject as an instance of both the class BookAboutLions and BookAboutAnimals. It will also be able to classify the class BookAboutLions defined above as a subclass of the class BookAboutAnimals (defined in a similar way).
- This approach is likely to be the easiest approach to use if you would like to employ DL reasoning to classify books based on their subjects.
- Many would consider it more cumbersome to express a simple fact that the subject of a book is "lions" by creating a new (usually, anonymous) restriction class and making that class to be the type of the book.

Summary: This approach can make the most use of DL reasoners. It represents a different interpretation of the subject as being a prototypical instance of a class rather than a whole class of things or a specific subject corresponding to that class. With the understanding that you are using a different interpretation, this approach may be a good one to use if using DL reasoners to classify individuals based on their subjects (or another property used in its place) is important.


### Approach 5: Use classes directly as annotation property values

![](/assets/images/2024-10-21-03-51-14.png)



- In OWL DL, annotation properties cannot at the same time be defined either object properties or datatype properties. Thus, if dc:subject (or another property you want to use) is defined elsewhere as an object property or a datatype property, it cannot be used as an annotation property.
- In OWL DL, annotation properties cannot have any restrictions, such as cardinality or domain/range restrictions, or subproperties. Thus, if you use this approach, you cannot specify that each book should have at least one subject for example or that individuals that are instances of BookAboutAnimals must all be subclasses of the Animal class.
- Even if the ontology is in OWL DL (i.e., the annotation properties are used consistent with OWL DL restrictions), DL reasoners will not use the information in annotation properties for reasoning. Thus, in order to extract a book about lions when queried for animal books, one would need to use special-purpose reasoning that uses annotation properties and can perform reasoning with them.

Summary: This approach allows you to use classes directly as property values while staying in OWL DL. However, the properties that will have classes as values will have to be defined as annotations and therefore cannot have any additional restrictions defined on them (and should not be declared as object or datatype properties elsewhere). DL reasoners will not use values of annotation properties.