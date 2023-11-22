---
id: 2yn4gyia85qoz22onz4k09a
title: Gaml
desc: 'GAma Modeling Language'
updated: 1697089275725
created: 1694708715914
---

- url: https://gama-platform.org/wiki/GamlLanguage

## #features

- species can be constructed in a compositional way with the notion of skills, bundles of attributes and actions that can be shared between different species and inherited by their children. ^8jzl8r4hwjj2


## [[c.model.conceptual]]
  
- defining a model in GAML amounts to defining a model species, which later allows to instantiate a model agent (aka a simulation), which may or may not contain micro-species, and which can be flanked by experiment plans in order to be simulated.

This conceptual structure is respected in the definition of model files, which follows a similar pattern:

    Definition of the global species, preceded by a header, in order to represent the model species
    Definition of the different micro-species (either nested inside the global species or at the same level)
    Definition of the different experiment plans that target this model

-    Since simulations, or experiments, are represented by agents, GAMA is bound to support high-level model compositionality, i.e. the definition of models that can use other models as inner agents, leveraging multi-modeling or multi-paradigm modeling as particular cases of composition.
    The visualization of models can be expressed by models of visualization, composed of agents entirely dedicated to visually represent other agents, allowing for a clear separation of concerns between a simulation and its representation and, hence, the possibility to play with multiple representations of the same model at once.

- The agent-oriented modeling paradigm means that everything "active" (entities of a model, systems, processes, activities, like simulations and experiments) can be represented in GAML as an agent (which can be thought of as a computational component owning its own data and executing its own behavior, alone or in interaction with other agents).
- Any species can be nested in another species (called its macro-species), in which case the populations of its instances will imperatively be hosted by an instance of this macro-species. A species can also inherit its properties from another species (called its parent species), creating a relationship similar to specialization in object-oriented design. In addition to this, species can be constructed in a compositional way with the notion of skills, bundles of attributes and actions that can be shared between different species and inherited by their children.