---
id: pfdqhyncw7rype44ediqswf
title: GFO
desc: 'General Formal Ontology'
updated: 1720242554715
created: 1709751631541
---

- url: 
  - https://raw.githubusercontent.com/Onto-Med/GFO/main/gfo-basic.owl
  - https://www.onto-med.de/sites/www.onto-med.de/files/files/uploads/Ontologies/gfo.owl
  - https://www.onto-med.de/ontologies/gfo#impl
- repo: 
  - https://github.com/Onto-Med/GFO
  - https://github.com/Onto-Med/GFO-2.0 (empty)
- related: [[prdct.gol]]

![](/assets/images/2024-03-07-13-47-05.png)
(heterarchy with multiple inheritance)

## Issues

- aren't "material processes" and "social processes" still processes?
- fine line between categories and attributives
  - "Categories provide the basic structure of the ontology, defining what kinds of things exist, whereas attributives are used to describe specific qualities or features of these things."
- 

## OWL

There is an OWL version of GFO, which currently comprises a stable core called gfo-basic.owl and a more extensive version called gfo.owl. The stable URLs to the current releases of these files are:

    http://www.onto-med.de/ontologies/gfo-basic.owl

    (version 1.0, build 13, 07.10.2008)
    http://www.onto-med.de/ontologies/gfo.owl

    (version 1.0, build 9, 28.08.2006)


## Features

-   coherent integration of objects and processes (based on a novel category of _persistants_)
-   time and space entities as entities sui generis, and the relation of _coincidence_
-   a category of _situoids_, comprehensible wholes of the most independent character
-   elaborate accounts of functions and roles
-   openness regarding philosophical positions such as realism, conceptualism, or nominalism by the provision of different kinds of categories as universals, concepts, or symbolic structures
-   levels of reality and ontological regions
-   three-layered meta-ontological architecture consisting of an abstract top level, an abstract core level, and a basic level.

## Philosophy

- It turns out that a top-level ontology being used as a monolithic system is not flexible enough to be easily adopted for particular application areas. Therefore, in the continued development of GFO we pursue a novel approach, organizing the ontology into modules related to ontological regions and their levels.
- the evolution of foundational ontologies is based on two primary stages of revision, (i) the integration stage and (ii) the expansion and reorganization stage. In the integration stage existing foundational ontologies are compared, interrela- tions between them are studied and ontological mappings between them are established. The expansion and reorganization step consists in the inclusion of new insights from science, society, and nature, and in the creation of new corresponding categories that cannot be reconstructed within the given systems. We call this type of knowledge dynamics the community-driven creative evolution of ontologies

## Details

- GFO distinguishes four modes of being, which are associated with the following ontological regions of the world: the region of ma- terial entities, the mental-psychological ontological region, the social region (involving socio-systemic entities), and the region of ideal entities, where the latter includes mathematical entities, idealizations, and ideas.
-  trichotomy of processes, continuants and presentials. The latter [presentials] can roughly be seen as snapshots of continuants at time points. The trichotomy comes with an integration law.
-  distinct notions of process and event: Processes form a central category of time-extended, immutable (can't change, but can contain changes) entities in GFO, whereas any event is relative to a process
- GFO provides a basic classification (ontology) of categories, whereas the notion of category covers all abstract entities that can be instantiated by or are predicated of other entities

### Space and Time

- Space and time are considered as categories, the instances of which are stipulated to be concrete individuals
  - Time comprises (a.o.) instances called chronoids, which may be understood as closely similar to real-valued intervals with endpoints. 
  - The category Space, called phenomenal space, exhibits space regions as instances of primary importance.

### Concrete Individuals

- there is a difference between a process boundary and a material structure. A material structure, being a snapshot / presential of a material object, contains only those qualities of the object that do not depend on a process. If we consider a moving ball B, then the presential of B at t contains qualities, such as its size, form, color, and mass. The process of the movement of the ball, restricted to a time point t, yields a process boundary that contains further qualities besides those mentioned, including the velocity and acceleration of the object at this time point.
- processes can never be wholly present at time points, whereas presentials possess this propert
- Processes form a subclass of processual complexes, which are the most general kind of concrete individuals that have a temporal extension. The temporal extension of a processual complex is a mereological sum of a non-empty set of chronoids. Cohesive processes form an important subclass of all processes: a process is cohesive if any two process boundaries are causally connected, if their temporal boundaries coincide
- Events are temporally localized at time boundaries. 
  - Another(?) type of event is a discrete change, for example, switching on the light in a dark room (understood to happen instantaneously
  - Histories present a further type of occurrents in that they form a sequence of process boundaries, for example, the sequence of measurements of blood pressure during a certain time interval. They y an important role in the investigation of time series
- Material situations are parts of the material world (at the macroscopic level) that can be consistently comprehended as a whole.
  -  We distinguish three kinds of situations: object situations, presentic situations, and situoids. 
     -  Object situations consist of material objects and relations between them. 
     -  A presentic situation is a snapshot of an object situation
     -  a situoid (or processual situation) is a part of the spatiotemporal world that arises from an object situation if all objects are replaced by the corresponding processes
        -  An example of a situoid is a football match, happening in time, and including all necessary participating entities, among them the players, the football, the goals and other entities, but also the localization and the corresponding environment(?)

### Complexity and Structure of Individuals

![](/assets/images/2024-03-12-16-29-53.png)

- One type of composition uses dependency relations that glue entities together, another
uses the part-of relation and the construction of mereological sums
  - Elementary individuals that are related to other individuals by some kind of dependency relation are called attributives. They include, among others, qualities, relators, roles, functions, dispositions, and structural features
  - Material objects are wholes consisting of bundles of attributives; furthermore, relational material facts are composed of material objects and relators, and material situations are composed of material facts. 
- for "We are aware of the problems related to bundle-theory. We agree essentially with the criticism by Gustav Bergmann [1967]" see [[sh.question-log.2024.03.12#what-are-gustav-bergmanns-criticisms-of-bundle-theory]]

#### Attributives

- an additional perspective on attributives – illustrated in Fig. 2 – has been developed as a foundation for an integrated data semantics
![](/assets/images/2024-04-05-13-01-16.png)
  - object attributives are only intrinsic
    - @chatgpt.4 an extrinsic attributive in programming or data modeling is an attribute of an object that is not inherent to the object itself but is instead derived from its relationship with other objects or external factors. For example, in a virtual role-playing game, consider an object like a 'sword.' Intrinsic attributes might be its weight, length, or material. An extrinsic attributive could be its 'reputation' which might be derived from its history in the game world (like the number of victories it's been used in or who previously owned it). This reputation isn't a physical property of the sword but is attributed to it based on external factors and relationships.
  - among object attributives we differentiate presentic and non-presentic ones. A presentic object attributive is determined fully and as a whole by the object it inheres in and a time during which itexists. For example, an individual color of red inhering in some object can be wholly accessed at time points.
  - "An ontology of attributives contributes to an ontology of data because most data should be understood as the result of measurements of attributives. "
- "A presentic object attributive is determined fully and as a whole by the object it inheres in and a time during which it exists. For example, an individual color of red inhering in some object can be wholly accessed at time points. "
  - a presentic object attributive thus gives rise to a continuant, on the one hand, which itself exhibits, at each time point of its lifetime, a wholly present attributive at that time (a presential).
  - Non-presentic object attributives inhere likewise in objects, but they require something in addition to just their bearer and a time point. For example, the age of an object at a certain point in time is not only determined by that object and that very time point, but it requires something else; say, the initial point in time of the object’s existence.
  - note that the composition of an object with some of its qualities yields more complex entities, called object facts.
- Processual attributives have processes and process boundaries as bearers and they are classified into presentic and global attributives. Presentic processual attributives are associated with process bound- aries; they must be wholly accessible at time points. The isolated presentic data of process boundaries do not need any reference to a process; they can be completely reduced to object qualities. These are typical qualities of objects that participate in the process. An example of a non-isolated presentic at- tributive of a process is the velocity of a moving body at a time point (even if it is zero, e.g. as an initial velocity). The velocity cannot be determined and specified without a temporally extended process.
- The global attributives of processes present the richest class of attributives of processes. A systematic classification of these attributives is in its initial stage. Their main feature is that it is not meaningful to specify or refer to them at a process boundary. One type of global attributives is abstracted from time se- ries in the form of diagrams (such as curve diagrams). Examples are electro-cardiograms and long-term blood pressure measurements.
  - " Additionally, we emphasize that intrinsic global attributives of processes are themselves processes, called attributive processes. A clear separation between an attributive process and a corresponding bearer-process needs further investigation and clarification. A water wave, for ex- ample, can be considered as an attributive process that occurs on the basic process of local movements of water particles. This basic process is the bearer of the wave"

- many other global attributives of a process are not derived from time series. Examples are the duration of a process and its occupied space. 
- There are further kinds of attributives, including relators, roles, functions, and dispositions, which are more abstract than phenomenal attributives; they cannot be directly perceived or measured.
- GFO adopts the general understanding of a role presented by Frank Loebe [2007], where a role individual is defined as a relational entity that links any entity, called the role player (or filler), with some context, in which the entity plays that role. The notion of role is essential for a broad spectrum of modeling areas, one of which supported by GFO is functional modeling. Its objective is to depict a domain in teleological / functional terms, as contrasted with other aspects, such as structural or behavioral ones.
  - The notion of function is built upon that of role: we introduce a function as a category that captures a role played by some entity in the context of a goal achievement (GA), where the GA provides a teleological specification of transitioning to something that is intended to be achieved.
- interfacing between attributives and knowledge occurs through the transformation from facts to propositions, and thus, in general, from data to knowledge. This transformation from a fact (being a part of reality) to a proposition is the (mysterious) pivot of the mind’s ability to transcend the sense-data to achieve a meta-level view on the world. This is an extraordinary ability of the human mind. 


## Formalization in FOL

- the integration law for objects and processes in GFO: For every material object there exists a uniquely determined process, the temporal extension of which equals the lifetime of the material object, and at every time point of that lifetime of the object the presential exhibited by the object is likewise the process boundary of that associated process (at the very same time point).
- 

### Integration Axiom

- For every material object there exists a uniquely determined process, the temporal extension of which equals the lifetime of the material object, and at every time point of that lifetime of the object the presential exhibited by the object is likewise the process boundary of that associated process (at the very same time point).
  -  In 4D ontologies, there are only processes, while material objects are considered as particular processes.
  -  In 4D ontologies,
there are only processes, while material objects are considered as particular processes.
  - 


## Situation vs Situoid vs Process vs Processual Complex 

- Situation: A situation is a static snapshot of reality, representing the state of affairs at a particular point in time. It encapsulates the relationships, properties, and configurations of entities without focusing on their temporal evolution. Situations are used to describe a particular set of circumstances or the way things are arranged at a specific moment.

- Situoid: a generalized or potential situation. It doesn't describe a specific state of affairs at a particular time; instead, it represents a type of situation that could occur under certain conditions. Situoids are useful for modeling hypothetical scenarios, possible states, or conditions that could exist given certain parameters.

- Process: A process, on the other hand, is dynamic and temporal. It refers to a series of events or actions unfolding over time. Processes are characterized by change, development, and the sequence of states they pass through. They emphasize the movement from one state to another and are essential for understanding phenomena that involve transformation or progression.

- Processual Complex: interdependent processes



## Concepts, Symbol Structures, and Platonic and Immanent Universals

- @gemini.1.5.advanced GFO accounts for different philosophical stances: It accommodates those who believe in the real existence of universals outside of minds (realism), those who view them as primarily mental (conceptualism), and those who emphasize representations (nominalism).



## References

- [[ar.gfo-the-general-formal-ontology]] 
- [[ar.towards-gfo-2-0-architecture-modules-and-applications]]
- http://www.thezfiles.co.za/ROMULUS/ontologicalCommitments.html
- [[ar.towards-ontological-foundations-for-conceptual-modeling-the-unified-foundational-ontology-ufo-story]]