---
id: 3ti1yijy5tvvcny1ene8kk6
title: Lexrdf Can Owl Class Be a Subclass of One of Its Own Instances
desc: ''
updated: 1728924486459
created: 1728924311202
---

- https://answers.knowledgegraph.tech/t/lexrdf-can-owl-class-be-a-subclass-of-one-of-its-own-instances/4651

## Discussion

- @antoine-zimmermann: First of all, when you talk about the semantics of OWL, there can be ambiguity because OWL has two different semantics. There is the direct semantics, which is based on Description Logics and applies to onolotgies that can be expressed in the functional syntax 1 of OWL, and the RDF-based Semantics 1, which is based on RDF and apply to any RDF document. In the case of your example, it does not make sense to talk about the direct semantics, as your ontology is not valid according to the functional syntax, but it represents a valid RDF document.

Now, in the [[RDF semantics|t.semantic-web.owl.rdf-based-semantics]], classes are instances of rdfs:Class and rdfs:Class is also a class so it is an instance of itself. No problem with that as RDF differenciates the class itself from the set of its instances. In the RDF-based semantics of OWL, owl:Class is equivalent to rdfs:Class so it is an instance of itself as well.