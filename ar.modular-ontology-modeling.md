---
id: jcbtfismirdgdb8o8urps4h
title: Modular Ontology Modeling
desc: ''
updated: 1728771275560
created: 1728769289325
---

- https://content.iospress.com/articles/semantic-web/sw222886

## Abstract

Reusing ontologies for new purposes, or adapting them to new use-cases, is frequently difficult. In our experiences, we have found this to be the case for several reasons: (i) differing representational granularity in ontologies and in use-cases, (ii) lacking conceptual clarity in potentially reusable ontologies, (iii) lack and difficulty of adherence to good modeling principles, and (iv) a lack of reuse emphasis and process support available in ontology engineering tooling. In order to address these concerns, we have developed the Modular Ontology Modeling (MOMo) methodology, and its supporting tooling infrastructure, CoModIDE (the Comprehensive Modular Ontology IDE – “commodity”). MOMo builds on the established eXtreme Design methodology, and like it emphasizes modular development and design pattern reuse; but crucially adds the extensive use of graphical schema diagrams, and tooling that support them, as vehicles for knowledge elicitation from experts. In this paper, we present the MOMo workflow in detail, and describe several useful resources for executing it. In particular, we provide a thorough and rigorous evaluation of CoModIDE in its role of supporting the MOMo methodology’s graphical modeling paradigm. We find that CoModIDE significantly improves approachability of such a paradigm, and that it displays a high usability.

## Highlights

### Introduction

- it is often much easier to develop a new ontology from scratch, than it is to try to re-use and adapt an existing ontology.
- four of the major issues preventing wide-spread re-use are (i) differing representational granularity, (ii) lack of conceptual clarity in many ontologies, (iii) lack and difficulty of adherence to established good modeling principles, and (iv) lack of re-use emphasis and process support in available ontology engineering tooling.
- If a use case requires fine-granularity data, a coarse-grained ontology is essentially useless. On the other hand, using a fine-grained ontology for a use case that requires only coarse granularity data is unwieldy due to (possibly massively) increased size of ontology and data graph.
- Even simple cases, such as the recommendation to not have perdurants and endurants together in subclass relationships
- “good modeling” appears to largely be a function of modeling experience and more of an art, than a science, which has not been condensed well enough into tangible insights that can easily be written up in a tutorial or textbook.
- Once a reusable ontology resource has been located, a suitable reuse method must first be selected; e.g., cloning the entire design into the target ontology/namespace, using owl:imports to include the entire source ontology as-is, cloning individual definitions, locally subsuming or aligning to remote ontology entities, etc.
- through ontology re-use, the ontologist commits to a design and logic built by a third party.
  - keeping track of the provenance of re-used ontological resources and their locally instantiated representations may become important,
  - This is particularly important in case remote resources are reused directly rather than through cloning into a local representation (e.g., using owl:imports or through alignments to remote entities using subclass or equivalence relations);
- The notion of module has taken on a variety of meanings in the Semantic Web community [2,18,60]. For our purposes, a module is a part of the ontology (i.e., a subset of the ontology axioms) which captures a key notion together with its key attributes. For example, an event module may contain, other than an Event class, also relations and classes designed for the representation of the event’s place, time, and participants.
- A module is thus as much a technical entity, in the sense of a defined part of an ontology, as well as a conceptual entity, in the sense that it should encompass different classes (and relationships between them) which “naturally” (from the perspective of domain experts) belong together.
- Modules may overlap. They may be nested. They provide an organization of an ontology as an interconnected collection of modules, each of which resonates with the corresponding part of domain conceptualization by the experts.
  - modules make it possible to approach ontology modeling in a divide-and-conquer fashion; first, by modeling one module at a time, and then connecting them
- The systematic use of [[ontology design patterns|t.cs.semantic-web.ontology.design-patterns]] [8,17] is another central aspect of our approach, as many of their promises resonate with the issues that our approach is addressing [28].


### Related Work

- The [[prdct.methontology]] methodology is presented by Férnandez et al. in [15]. It is one of the earlier attempts to develop a development method specifically for ontology engineering processes
- The [[prdct.on-to-knowledge]]  Methodology (OTKM) [61] is, similarly to METHONTOLOGY, a methodology for ontology engineering that covers the big steps, but leaves out the detailed specifics.
- [[ar.distributed-engineering-of-ontologies-diligent]], by Pinto et al. [43], is an abbreviation for Distributed, Loosely-Controlled and Evolving Engineering of Ontologies, and is a method aimed at guiding ontology engineering processes in a distributed Semantic Web setting
- In all three of these well-established methods, the process steps that are defined are rather coarse-grained. They give guidance on overall activities that need to be performed in constructing an ontology, but more fine-grained guidance (e.g., how to solve common modeling problems, how to represent particular designs on concept or axiom level, or how to work around limitations in the representation language) is not included. 

#### Ontology Design Patterns

- Ontology Design Patterns (ODPs) were introduced at around the same time independently by Gangemi [17] and Blomqvist and Sandkuhl [8]
- Key contributions include the eXtreme Design methodology (detailed in Section 2.3) and several other pattern-based ontology engineering methods (Section 2.4). The majority of work on ODPs has been based on the use of miniature OWL ontologies as the formal pattern encoding, but there are several examples of other encodings, the most prominent of which are OPPL [14] and more recently OTTR [59].
- MOMo extends on those methods, but also incorporates results from our past work on how to document ODPs [26,29,32], how to implement ODP support tooling [22] and how to instantiate patterns into modules by “stamping out copies” [24].
- [[prdct.samod-methodology]] [42], or Simplified Agile Methodology for Ontology Development, is a recently developed methodology that builds on and borrows from test-driven and agile methods (in particular eXtreme Design). SAMOD emphasises the use of tests to confirm that the developed ontology is consistent with requirements, and prescribes that the developer construct three types of such tests: model tests, data tests, and query tests.

#### Graphical Conceptual Modeling

- [[prdct.comodide]] has taken influence from [[prdct.vowl]], e.g., in how we render datatype nodes. However, in a collaborative editing environment in which the graphical layout of nodes and edges needs to remain consistent for all users, and relatively stable over time, we find the force-directed graph structure (which changes continuously as entities are added/removed) to be unsuitable.
- the commercial offering [[prdct.grafo]]55 offers a very attractive feature set, combining the usability of a VOWL-like notation with stable positioning, and collaborative editing features. Crucially, however, Grafo does not support pattern-based modular modeling or import statements, and only supports RDFS semantics, and as a web-hosted service, does not allow for customizations or plugins that would support such a modeling paradigm.
- CoModIDE is partially based on the Protégé plugin , as presented in [47]. OWLAx plugin supports one-way translation from graphical schema diagrams drawn by the user, into OWL ontology classes and properties; however, it does not render such constructs back into a graphical form. There is thus no way of continually maintaining and developing an ontology using only OWLAx. There is also no support for design pattern re-use in this tool.


### 3 The modular ontology modeling methodology (MOMo)

![](/assets/images/2024-10-12-15-12-34.png)


#### 3.3 OWL axioms

axiomatizations can have different interpretations, and while they can, for example, be used for performing deductive reasoning, this is not their main role as part of the MOMo approach. Rather, for our purposes axioms serve to disambiguate meaning, for a human user of the ontology.

## References

[^23]: K. Hammar, Content ontology design patterns: Qualities, methods, and tools, PhD thesis, Linköping University, Sweden, 2017. doi:10.3384/diss.diva-139584.
