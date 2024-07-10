---
id: og9wupt76m9mjpcc57ewdzy
title: DESO
desc: >-
  a foundational ontology for discrete event system modeling derived from the
  foundational ontology UFO
updated: 1713381693514
created: 1712868523749
---

- related: [[prdct.unified-foundational-ontology]]
- purpose: provide a basis for evaluating discrete event simulation languages

## Ontologies

- see [[sh.question-log.2024.04.17#why-does-the-deso-discrete-event-simulation-ontology-separate-run-time-from-design-time-ontologies]]

### Runtime Ontology (DESO-I)

![](/assets/images/2024-04-17-12-07-42.png)

- (physical) objects
- situations and object snapshots
- In DESO-I, for simplicity, we assume that there are only binary material relationships, which are represented by references specifying a value for a reference property. (boo!)
- A slot is either a reference or an attribution (an attribute-value pair).

### Design-Time Ontology (DESO-U)
![](/assets/images/2024-04-17-12-12-35.png)

- entity types


## Evaluating DES Languages

There are four properties of a simulation language to be checked in its evaluation:
1. Soundness: L is sound w.r.t. DESO iff every element of L has an interpretation in terms of a do- main concept from DESO. The degree of soundness can be measured relatively as the number of L elements that have a DESO interpretation divided by the total number of L elements.
2. Completeness: L is complete w.r.t. DESO iff every DESO concept is represented by a modeling primitive of L. The degree of completeness can be measured relatively as the number of DESO concepts that are represented by an element of L divided by the total number of DESO concepts.
3. Lucidity: L is lucid w.r.t. DESO iff every element of L has at most one interpretation in DESO. The degree of lucidity can be measured relatively as the number of L elements that have at most one interpretation in DESO divided by the total number of L elements.
4. Laconicity: L is laconic w.r.t. DESO iff every domain concept from DESO is represented by at most one element of L. The degree of laconicity can be measured relatively as the number of DESO concepts that are represented by at most one element of L.



## References

- [[ar.towards-an-ontological-foundation-of-discrete-event-simulation]]

DESO, a foundational ontology