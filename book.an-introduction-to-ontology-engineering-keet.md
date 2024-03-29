---
id: o0i0slyae40yf3o4crroqes
title: An Introduction to Ontology Engineering Keet
desc: ''
updated: 1711699334937
created: 1711471328539
---

- url: https://eng.libretexts.org/Bookshelves/Computer_Science/Programming_and_Computation_Fundamentals/An_Introduction_to_Ontology_Engineering_(Keet)/
- https://people.cs.uct.ac.za/~mkeet/files/OEbook.pdf
- author: @maria-keet
- related: [[prdct.onset]]

## Highlights

- if one indeed aims for the purposes of interoperability and reusability across applications by means of an ontology, then don’t use data properties and data types.
  - The idea is to generalize (more precisely: reify) the attribute into a class so that we can reuse the core notion that is the same throughout (Color and Weight in the examples), and this new entity is then related to the endurants and perdurants on the one side and instead of datatypes, we use value regions on the other side. Thus, an unfolding from one attribute/OWL data property into at least two properties: there is one OWL object property from the endurant/perdurant to the reified attribute—a quality property, represented as an OWL class—and a second object property from quality to the value region. In this way, the shared understanding can be shared, and any specifics on how one has to store the data is relegated to the implementation, therewith solving the problem of the limited reusability of attributes and preventing duplication of data properties. For instance, Color would be a subclass of Quality in DOLCE [MBG+03] and a Specifically dependent continuant in BFO. An example of the approach taken in DOLCE is depicted in Figure 6.1.2: rose1 is an instance of Rose, which is a subclass of NonAgentive Physical Object, and it is related by the qt relation to its colour property, c1, which is an instance of the quality Color that is a subclass of Physical Quality. The actual value—the [measured] redness—of the color of the rose at a given time is a region red color as instance of the Color Region, which is a subclass of Physical Region, and they are related by means of the q|t relation4.