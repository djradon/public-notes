---
id: tqj6kdyaahl2jwfa2o0rlos
title: Spin
desc: >-
  sparql inferencing notation is the de-facto industry standard to represent
  SPARQL rules and constraints on Semantic Web models
updated: 1722756483532
created: 1714576388204
---

- https://spinrdf.org/
- similar: [[prdct.shacl]]
- aka: SPARQL rules

## Implementations

- [[prdct.allegrograph]]
- [[prdct.rdf4j]] but "The use of SPIN is no longer recommended."
- [[prdct.topbraid-composer]]

## Uses

- Calculate the value of a property based on other properties - for example, area of a geometric figure as a product of its height and width, age of a person as a difference between today's date and person's birthday, a display name as a concatenation of the first and last names
- Isolate a set of rules to be executed under certain conditions - for example, to support incremental reasoning, to initialize certain values when a resource is first created, or to drive interactive applications
- SPIN offers a way to do constraint checking with closed world semantics and automatically raise inconsistency flags when currently available information does not fit the specified integrity constraints. Constraints are specified using SPARQL ASK or CONSTRUCT queries, or corresponding SPIN Templates.


## Comparisons

### SPIN vs SHACL

- SHACL offers much greater flexibility w.r.t. the application target of constraints (and rules). While SPIN is limited to classes, SHACL shapes can be applied to either classes or sets of nodes derived by other means. See the various [target mechanisms](https://www.w3.org/TR/shacl/#targets) in SHACL, including the [custom targets](https://www.w3.org/TR/shacl-af/#targets) from the Advanced Features document.
- "SHACL should be regarded as the next generation of SPIN. Learn how they compare."

### SPIN vs SWRL

- "However, we believe that SPIN is superior to SWRL in almost every respect, mainly because SPIN is based on SPARQL. SPARQL is well established and supported by numerous engines and databases. This means that SPIN rules can be directly executed on the databases and no intermediate engines with communication overhead need to be introduced. Also, SPIN is more expressive than SWRL, because SPARQL has various features such as UNIONs and FILTER expressions. SPIN has an object-oriented model that arguably leads to better maintainable models than SWRL's flat rule lists. Finally, SPIN goes far beyond being just a rule language, and also provides means to express constraints and to define new functions and templates."


## References

- https://spinrdf.org/spin-shacl.html
- https://medium.com/virtuoso-blog/virtuoso-8-0-creating-a-custom-inference-rules-using-spin-vocabulary-d7a060f859ef
- https://spinrdf.org/faq.html