---
id: 3oygg06p6jjbt68la0azf1f
title: eUFO
desc: 'essential Unified Foundational Ontology'
updated: 1713381663269
created: 1712868624751
---

## References

- [[ar.towards-an-ontological-foundation-of-discrete-event-simulation]]

## Terms

- **substance individuals**: things with spatio-temporal qualities, founded on matter
- **trope individuals**: things that inhere in substance-individual bearers
  - **intrinsic**: qualities
    - non-migration (or non-transferability) principle: it is not possible for a particular quality q to inhere in two different individuals a and b
    - distinguish between the color of a particular apple (its quality) and the ‘color data value’ that we associate with this quality in an **attribution** (with the help of an **attribute**)
      - we may associate more than one attribute with a particular quality universal, each of them based on a different datatype. E.g., the quality universal “hair color” could be captured by an attribute with the range of RGB byte triples or by an attribute with the range of natural language color names. 
  - **relators**: things that depend on two or more substance-individuals

### Relators, Material Relationships and Reference Properties

- in general, relators are founded on events
  - e.g. a particular marriage is founded on a marriage ceremony
- material relationships depend on relators to exist; (i.e., a particular marriage depends on the relator "marriage"?)

### Events

- Events are ontologically dependent entities in the sense that they existentially depend on their participants in order to exist.
- Events may change the real world by changing the state of affairs from one (pre-state) situation to a (post-state) situation.
  - Each situation is determined by a set of associated object snapshots and a set of associated material relationships holding between the involved objects, 
- Being atomic and being instantaneous are orthogonal notions in this framework, i.e., an atomic event can be time-extended and an instantaneous event can be composed of multiple (instantaneous) events.
- All spatial properties of events are defined in terms of the spatial properties of their participants. In contrast, all temporal properties of objects are defined in terms of the events in which they participate.
- The temporal attributes of events have values from special temporal datatypes. We assume that these da- tatypes support the concept of Time Intervals, which are composed of Time Points. Time points could be represented as real numbers and Time Intervals as sets of real numbers. However, they could also be de- fined in other ways (we avoid making unnecessary ontological commitments at this point). Additionally, we admit: (i) intervals that are delimited by begin and end points as well as open intervals; (ii) continuous and non-continuous intervals; (iii) intervals with and without duration (instants). In particular, this model allows a diversity of temporal structures such as linear, branching, parallel and circular time

#### Universals

- Universals classify individuals, which are said to be their instances. The set of all instances of a universal
is called its extension. We consider five kinds of universals: event types, object types, quality universals,
attributes, relator universals, reference properties and material relationship types.
![](/assets/images/2024-04-17-11-29-15.png)

##### Kinds of Object Types


![](/assets/images/2024-04-17-11-36-55.png)


- **sortal types** carry a principle of identity for
their instances
  - **principle of application** allows to judge whether an individual is an instance of that object type
  - a **principle of identity** allows to judge whether two individuals are the same
  - **base types**: Within the category of sortal types, we make a further distinction based on the formal notions of rigidity and anti-rigidity: A sortal type U is rigid if for every instance x of U, x is necessarily (in the modal sense) an instance of U. In other words, if x instantiates U in a given world w, then x must instantiate U in every possible world w’.
  - **role types**: involves extrinsic (relational) properties of R
    - For any role type (e.g. Student) there is an underlying binary material relationship type or refer- ence property (e.g. students) such that the extension of the role type (e.g. the set of current students of an educational institution) is the range of that reference property.
  - **phase types**: a condition that involves only intrinsic properties of P.
- Non-sortal types, such as RedThing, are called **mixin types**

##### Object type principles

1. Every object must instantiate exactly one ultimate base type.
2. A rigid object type cannot be a subtype of an anti-rigid object type (e.g., Person cannot specialize
Student).
3. A mixin type cannot be specialized by a sortal type (e.g., Person cannot specialize Customer).
4. A mixin type cannot have direct instances.

##### Quality Universals

- A quality universal classifies individual qualities of the same type. A quality universal can be associated with one or more datatypes, such that any particular quality corresponds to a specific data value from the value space of the datatype. The association between qualities of some quality universal and the corres- ponding data value from an associated datatype is provided by an attribute.

##### Relator Universals, Material Relationship Types and Reference Properties

- A relator universal classifies individual relators of the same type. The material relationship type R induced by a relator universal R classifies all material relationships induced by relators from R.
- A reference property represents a binary material relationship type, corresponding to a relator universal whose instances mediate exactly two objects.

## Thoughts

- why separate design-time and run-time?
- "Notice that in conceptual modelling, and in simulation modelling, we are not really interested to con-
sider all the things that constitute a real-world system. We call those things, in which we are interested,
entities, including: physical objects, events and certain material relationships. This choice implies that we
do not want to include amounts of matter, relators or qualities in a simulation model."
  - relators: a kiss, a covalent bond, a medical treatment, a purchase order, or a social commitment.
  - why wouldn't you want to include relators and qualities in a simulation model?
    - e.g. an attack; an equipped weapon?
- Sortal types are confusing... two Apples are the same?
- Base types: Person, but... in a fantasy world, even a creature could be transformed into a lamp
  