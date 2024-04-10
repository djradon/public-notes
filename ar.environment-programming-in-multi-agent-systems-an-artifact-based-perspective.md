---
id: 45iiar5pg6hcwztxbpitk2j
title: Environment Programming in Multi Agent Systems an Artifact Based Perspective
desc: ''
updated: 1712778696233
created: 1712683661437
---

- url: https://www.researchgate.net/publication/220660578_Environment_programming_in_multi-agent_systems_An_artifact-based_perspective

## Abstract

This article introduces the notion of environment programming in software multiagent systems (MAS) and describes a concrete computational and programming model based on the artifact abstraction and implemented by the CArtAgO framework. Environment programming accounts for conceiving the computational environment where agents are situated as a first-class abstraction for programming MAS, namely a part of the system that can be designed and programmed—aside to agents—to encapsulate functionalities that will be exploited by agents at runtime. From a programming and software engineering perspective, this is meant to improve the modularity, extensibility and reusability of the MAS as a software system. By adopting the A&A meta-model, we consider environments populated by a dynamic set of computational entities called artifacts, collected in workspaces. From the agent viewpoint, artifacts are first-class entities of their environment, representing resources and tools that they can dynamically instantiate, share and use to support individual and collective activities. From the MAS programmer viewpoint, artifacts are a first-class abstraction to shape and program functional environments that agents will exploit at runtime, including functionalities that concern agent interaction, coordination, organisation, and the interaction with the external environment. The article includes a description of the main concepts concerning artifact-based environments and related CArtAgO technology, as well as an overview of their application in MAS programming.


## Highlights

- the environment can be used to design and program the computational part of the system that is functional to agents’ work, i.e. that agents can dynamically access and use to exploit some kind of functionality, and possibly adapt to better fit their actual needs. 
-  some desiderata on programming/computational models can be identified:

  - Abstraction: The model adopted should preserve the agent abstraction level, i.e. the main concepts used to program environment structure and dynamics should be consistent with agent concepts and their semantics. Exam- ples include the notion of actions, percepts, events, tasks/goals. 
  - Orthogonality: The model should be as much orthogonal as possible to the mod- els, architectures, languages adopted for agent programming, so as to naturally support the engineering of heterogeneous systems. Generality: The model should be general and expressive enough to allow for developing different kinds of environment according to different application domains and problems, exploiting the same basic set of concepts and constructs.
  - Modularity: The model should introduce concepts to modularise environments, avoiding monolithic and centralised views.
  - Dynamic extensibility: The model should support the dynamic construction, replacement, extension of environment parts, in an open system perspective.
  - Reusability: The model should promote the reuse of environment parts in different application contexts/domains.
- existing program- ming paradigms can be re-used to define the environment programming model only by bridg- ing the abstraction gap that exists with respect to the agent abstraction level. 
  - e.g.
    -  the notion of object as defined in the context of object-oriented programming (OOP) cannot be re-used “as it is” as first-class environment abstraction: on the one side, in OOP objects inter- act with each other by means of method invocation and no action/perceptions concepts are defined; on the other side, method invocation is not defined in the context of agent-oriented programming and in the semantics of agent programming languages, consequently it is not meaningful to simply enable “agent–object interaction” in terms of method invocation. This holds also when considering agent frameworks based on OO programming languages, such as Jade [1] (which is based on Java): objects (classes) are used to implement agents, not to create environments shared by agents to enhance their coordination and cooperation—agents are meant to interact solely by means of message passing based on FIPA ACL. In other words: objects are not first-class entities of the agent world, they are the basic construct to implement agents. So, also in this case a further abstraction layer is necessary to wrap objects, defining the semantics of agent–object interaction.
-  

### Main Aspects of computational model for environment programming

#### Action Model

- in order to know if the execution of an action in the environment has been completed with success, an agent must check its percepts.
- the set of actions can be considered
part of the contract that the environment provides to the agents that are logically situated in it
- current agent programming languages models actions as events, i.e. as a single atomic transition (from the agent viewpoint) changing/inspecting the state of the environment. In this case it is like to say that actions have zero time length and the execution of two actions cannot overlap in time.
  - programmable environments make it possible to introduce richer semantics, modelling action execution as a process, i.e., a sequence of two or more events, including the event representing the starting of the action execution and the event represent- ing the completion of the execution. This allows for easily representing long-term, possibly concurrent actions and also to define actions useful for agent synchronisation

#### Perception Model

- 