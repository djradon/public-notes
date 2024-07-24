---
id: o0i0slyae40yf3o4crroqes
title: An Introduction to Ontology Engineering Keet
desc: ''
updated: 1721846392403
created: 1711471328539
---

- url: https://eng.libretexts.org/Bookshelves/Computer_Science/Programming_and_Computation_Fundamentals/An_Introduction_to_Ontology_Engineering_(Keet)/
- https://people.cs.uct.ac.za/~mkeet/files/OEbook.pdf
- author: @maria-keet
- related: [[prdct.onset]]

## Highlights

- if one indeed aims for the purposes of interoperability and reusability across applications by means of an ontology, then don’t use data properties and data types.
  - The idea is to generalize (more precisely: reify) the attribute into a class so that we can reuse the core notion that is the same throughout (Color and Weight in the examples), and this new entity is then related to the endurants and perdurants on the one side and instead of datatypes, we use value regions on the other side. Thus, an unfolding from one attribute/OWL data property into at least two properties: there is one OWL object property from the endurant/perdurant to the reified attribute—a quality property, represented as an OWL class—and a second object property from quality to the value region. In this way, the shared understanding can be shared, and any specifics on how one has to store the data is relegated to the implementation, therewith solving the problem of the limited reusability of attributes and preventing duplication of data properties. For instance, Color would be a subclass of Quality in DOLCE [MBG+03] and a Specifically dependent continuant in BFO. An example of the approach taken in DOLCE is depicted in Figure 6.1.2: rose1 is an instance of Rose, which is a subclass of NonAgentive Physical Object, and it is related by the qt relation to its colour property, c1, which is an instance of the quality Color that is a subclass of Physical Quality. The actual value—the [measured] redness—of the color of the rose at a given time is a region red color as instance of the Color Region, which is a subclass of Physical Region, and they are related by means of the q|t relation4.

### Using Perdurant/Occurent objects instead of property-verbs

- results in a more compact representation, is intuitively closer to the domain expert’s understanding, and makes it easier to verbalize the ontology, and therefore is likely to be more useful in praxis. The Running option is more generic, and thereby likely to increase reusability of the ontology. No scientific experiments have been conducted to test which way would be better to represent such knowledge, and current mapping tools do not deal with such differences of representing roughly the same knowledge in syntactically very different ways. Theoretical foundations for mappings between such distinct modeling styles have been proposed [^FK17], and this may be resolved soon.

### Time and Temporal Ontologies

- There are multiple requests for including a temporal dimension in OWL. Some of those requirements are described in the ontology’s annotation fields (see the OWL files of BFO and DOLCE), or the labels of the object properties in the BFO v2.1 draft, where they mention temporality that cannot be represented formally in OWL: ^k691d5r7ug82
  - DOLCE has a temporally indexed parthood in the paper-based version but this could not be transferred into the OWL file.
- there is no single computational solution to solve these examples all at once in another way beyond OWL. Thus far, it is a bit of a patchwork of various theo- ries and some technologies, with, among many aspects, the [[Allen’s interval algebra|t.cs.time.allens-interval-algebra]] with the core qualitative temporal relations (such as before and during), [[Linear Temporal Logics|prdct.ltl-linear-temporal-logics]] (LTL) and Computational Tree Logics (CTL, with branch- ing time). 
  - some might say [[t.cs.time.allens-interval-algebra]] are all the temporal relations one will ever need, but one may wish to be more specific in specialised subject domains, such as a transformation of a caterpillar into a butterfly, not just that a butterfly was a caterpillar ‘before’, and one thing developed from another thing in developmental biology.
- Modellers want to do even more than that: temporalising classes and relations. The former is well-known in databases as ‘object migration’; e.g., an active project evolves to a completed project, and each divorcee in the census database must have been married before. Relation migration follows the idea of temporal classes, but applies to n-ary tuples (with n ≥ 2); e.g. ‘during x’s lifetime, it always has y as part’ and ‘every passenger that boards the plane must have checked in before departure of that flight’.


#### Temporal DLs

- A very expressive (undecidable) DL language is [[prdct.dlrus]] (with the Until and Since operators), which already has been used for temporal conceptual data modelling [APS07] and for representing essential and immutable parts and wholes [AGK08], which also solves the Boxer example of Section 6.2. It uses linear time and mostly qualitative temporal constraints.
- [[ar.temporal-representation-and-reasoning-in-owl-2]]


## References

[^FK17]: [FK17] Pablo R. Fillottrani and C. Maria Keet. Patterns for heterogeneous tbox mappings to bridge different modelling decisions. In E. Blomqvist et al., editors, Proceeding of the 14th Extended Semantic Web Conference (ESWC’17), volume 10249 of LNCS, pages 371–386. Springer, 2017. 30 May - 1 June 2017, Portoroz, Slovenia.
- 
