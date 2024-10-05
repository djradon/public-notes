---
id: stdy7h7as46ehxupm66538k
title: Reasoner
desc: 'the most expressive knowledge representation language anyone knows how to design while still preserving practical reasoning.'
updated: 1728144324526
created: 1698706449311
---

## Decidability

- [[prdct.owl.dl]] is decidable
  - "There are many things systems engineers care about that are beyond the reasoning power of Description Logic. DL reasoners cannot solve differential equations, for example. But a great deal of what we care about, including the structure of systems of differential-algebraic equations can be expressed in assertions about types, properties, and relationships, and OWL reasoning can help us. In these situations we may use a specialized reasoner (e.g., Mathematica) to solve a problem, but a DL-based front end can help us construct the problem efficiently and with confidence in its correctness."

## Implementations

### Open-Source

-   [Cwm](https://en.wikipedia.org/wiki/Cwm_(software) "Cwm (software)"), a forward-chaining reasoner used for querying, checking, transforming and filtering information. Its core language is RDF, extended to include rules, and it uses RDF/XML or N3 serializations as required.
-   [Drools](https://en.wikipedia.org/wiki/Drools "Drools"), a forward-chaining inference-based rules engine which uses an enhanced implementation of the [Rete algorithm](https://en.wikipedia.org/wiki/Rete_algorithm "Rete algorithm").  
    -   also, [[prdct.drools.swrlapi]]
-   [Evrete](https://www.evrete.org), a forward-chaining Java rule engine that uses the [Rete algorithm](https://en.wikipedia.org/wiki/Rete_algorithm "Rete algorithm") and is compliant with the Java Rule Engine API (JSR 94).
-   [D3web](https://en.wikipedia.org/wiki/D3web "D3web"), a platform for [knowledge-based systems](https://en.wikipedia.org/wiki/Knowledge-based_systems "Knowledge-based systems") ([expert systems](https://en.wikipedia.org/wiki/Expert_systems "Expert systems")).
-   [Flora-2](https://en.wikipedia.org/wiki/Flora-2 "Flora-2"), an object-oriented, rule-based knowledge-representation and reasoning system.
-  [[prdct.jena]] [Jena](https://en.wikipedia.org/wiki/Jena_(framework) "Jena (framework)"), an open-source semantic-web framework for Java which includes a number of different semantic-reasoning modules.
-   [NRules](https://github.com/NRules/NRules) a forward-chaining inference-based rules engine implemented in [C#](https://en.wikipedia.org/wiki/C_Sharp_(programming_language) "C Sharp (programming language)") which uses an enhanced implementation of the [Rete algorithm](https://en.wikipedia.org/wiki/Rete_algorithm "Rete algorithm")
-   [Prova](https://en.wikipedia.org/wiki/Prova "Prova"), a semantic-web rule engine which supports data integration via SPARQL queries and type systems (RDFS, OWL ontologies as type system).
-   [DIP](https://github.com/kodymoodley/defeasibleinferenceplatform), Defeasible-Inference Platform (DIP) is an [Web Ontology Language](https://en.wikipedia.org/wiki/Web_Ontology_Language "Web Ontology Language") reasoner and [Protégé](https://en.wikipedia.org/wiki/Prot%C3%A9g%C3%A9_(software) "Protégé (software)") desktop plugin for representing and reasoning with defeasible subsumption.<sup id="cite_ref-3" class="reference"><a href="https://en.wikipedia.org/wiki/Semantic_reasoner#cite_note-3">[3]</a></sup> It implements a [Preferential entailment](https://en.wikipedia.org/wiki/Preferential_entailment "Preferential entailment") style of reasoning that reduces to "classical entailment" i.e., without the need to modify the underlying decision procedure.

### from awesome-ontology

-   [CEL](https://julianmendez.github.io/cel/) - A lightweight Description Logic (EL+) reasoner for large-scale biomedical ontologies. (Common Lisp+Java)
-   [ELK](https://github.com/liveontologies/elk-reasoner) - An ontology reasoner that aims to support the OWL 2 EL profile. (Java)
-   [EYE](https://github.com/josd/eye) - A reasoning engine which performs semibackward chaining and supports Euler paths. (Prolog)
-   [FaCT++](http://owl.man.ac.uk/factplusplus/) - The new generation of the well-known [FaCT](http://www.cs.man.ac.uk/~horrocks/FaCT) OWL-DL reasoner which uses optimised tableaux algorithms. (C++)
-   [Flora-2 (Ergo Lite)](http://flora.sourceforge.net/) - A F-logic based reasoning system. (Prolog)
-   [HyLAR](https://github.com/ucbl/HyLAR-Reasoner) - A rule-based incremental reasoner for the Web. (JavaScript)
-   [jcel](https://github.com/julianmendez/jcel) - A reasoner for the description logic EL+. (Java)
-   [Openllet](https://github.com/Galigator/openllet) - An OWL DL reasoner build on top of Pellet 2. (Java)
-   [OWL-RL](https://github.com/RDFLib/OWL-RL) - A simple implementation of the OWL2 RL Profile, as well as a basic RDFS inference, on top of RDFLib. (Python)
-   [pyfactxx](https://github.com/tilde-lab/pyfactxx) - Python bindings for upgraded FaCT reasoner and RDFLib integration. (Python/C++)
-   [Racer](https://www.ifis.uni-luebeck.de/~moeller/racer/) - A knowledge representation system that implements a highly optimized tableau calculus for the description logic SRIQ(D). (Common Lisp+Java)
-   [Whelk](https://github.com/balhoff/whelk) - A Scala OWL reasoner based on the algorithm implemented in ELK, using immutable data structures.

## References

- https://www.opencaesar.io/blog/2021/06/19/OML-Origin-and-Rationale.html
- http://owl.cs.manchester.ac.uk/tools/list-of-reasoners/