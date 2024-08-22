---
id: t2y8kcts8fbtx617z7yeqj8
title: Work
desc: ''
updated: 1724344182316
created: 1724342230699
---

- https://www.isko.org/cyclo/work

## Highlights

- "the essence of a creation, such as a novel, a symphony, a painting, a statue, a thesis, etc., intended by its creator to be communicated with some audience"
  - maybe the creator is his own audience
- consists of abstract intellectual content that is distinct from any object that is its carrier

### Properties of works

- For every two or three one-off books there is a work like Steinbeck’s Grapes of Wrath that exists in hundreds of editions, and translations, and becomes a screenplay, a motion picture, and so on
  - The first-published iteration of a work in such a set has been termed the **progenitor**
- We have seen above the two main categories of instantiation — derivation and mutation. From research it has been demonstrated that bibliographic works have at least the following types (Smiraglia 2002, 11):

    Derivations
        simultaneous editions
        successive editions
        predecessors
        amplifications
        extractions
        accompanying materials
        musical presentation
        notational transcription
        persistent works
    Mutations
        translations
        adaptations
        performances
- Furner demonstrates that the relationship between two documents that might be instantiations of the same work has the same identity as the relationship between two documents that might be about the same concept, because they are both members of the same class (12):

> If I decide that Doc 1 instantiates Work A, what that amounts to is a judgment — an entirely subjective judgment made by me on a particular occasion — that Doc 1 has the property of being an instance of Work A, that Doc 1 is a member of the class of documents that share the property of instantiating Work A \[…\] These are just different ways of saying the same thing, and again we can also say that Doc 1 and Doc 2 are similar in the sense that they share the same property or that they are members of the same class. And again, if it turns out that Work B has exactly the same extension as Work A does — in other words, if it turns out that all and only the documents that instantiate Work A instantiate Work B — then we can say that Work A is the same work as Work B.

A related aspect of the phenomenon of instantiation is the re-presentation of content, and it is this property that is endemic in the incorporation of information objects in retrieval systems in which large clusters of seemingly similar content must be simultaneously gathered and disambiguated. Empirical analysis of this phenomenon in museums and archives demonstrated the means by which not only visual representations of specific objects but also metadata associated with them require control — gathering and disambiguation — around a nominal anchor that usually is the identifier for the work 

- probably the most important empirical finding from the empirical research is the discovery that there is a cultural catalyst for the growth of a family of works all derived from a common progenitor. Initially, borrowing a phrase from Wilson (1968), these were called “bibliographic families”. In Functional Requirements for Bibliographic Records (FRBR, IFLA 1998) they are called “superworks”. These are works like Gone with the Wind that have achieved iconic status, and thus for which potentially thousands of iterations have come forth, all of which can be associated with a common progenitor through shared ideational and semantic content (Smiraglia 2007a). Nonetheless, not everything in the superwork set Gone with the Wind is equivalent with Margaret Mitchell’s novel. Instead, ideational nodes within the set (such as a screenplay) are related works that have their own instantiation sets. The problem for information retrieval, as stated earlier, is to simultaneously collocate and disambiguate these large sets of instantiations.

![](/assets/images/2024-08-22-09-20-48.png)


## The FRBR conceptual model and RDA

- for [[prdct.frbr]], manifestations reside in specific, physical items
- Change in ideational content results in a new work, change in semantic content results in a new expression, and the role of the publisher who brings an expression to market is recognized in the production of manifestations.

### Issues with FRBR

- precise implementation of the expression entity
- gaps in the model, principally for aggregate works
  - A conceptual model consisting of three types of aggregation — collections, augmentation aggregates and parallels — was reported in O’Neill and Žumer (2012)
- Many of these problems have been tackled in a reinterpretation of the FRBR conceptual model from its original entity-relationship model into an object oriented model, FRBRoo or [[prdct.lrmoo]]  