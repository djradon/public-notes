---
id: 1c425wcbnwh1esyiwydx1pw
title: Owl
desc: Web Ontology Language
updated: 1718080423423
created: 1696270955675
---


- url: https://www.w3.org/OWL/

## description:

- OWL 2 ontologies themselves are primarily exchanged as RDF documents
- OWL-Lite is the least expressive sub-langauge. OWL-Full is the most expressive sub-language. The expressiveness of OWL-DL falls between that of OWL-Lite and OWL-Full. 
 
## Highlights

- OWL ontologies can use the preexisting OWL attribute owl:versionInfo to store version information.

## Cons

-  A second major feature that proves troublesome is the monotonic nature of the inheritance of imported information. The ability to import other ontologies is crucial to supporting reuse of information. But all such inheritance is monotonic—in other words, new information can be added, but none of the existing information can be retracted or overridden. This makes it imperative that one make sure that all assertions are made at the proper level in the inheritance structure. If assertions are added at too low a level, then no sharing takes place. If made too high up, then the information cannot be removed, which can limit the ability to share knowledge and settings. It is difficult, even for experienced users, to decide where new knowledge should be created.
   -  The monotonic requirement also makes it impossible to have actual default values, since any such value could not be removed. We are able to avoid that problem through the use of meta-annotations that associate default values not with the individuals, but instead attach them to the properties themselves.

## [[c.product.related]]

- [[prdct.mod-ontology]]

## References

- [When owl:sameAs isn’t the Same: An Analysis of Identity
Links on the Semantic Web](https://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=B68E7B90BD3F8C5DAA756255722B7E78?doi=10.1.1.451.7903&rep=rep1&type=pdf)
- https://enterprise-knowledge.com/top-5-tips-for-managing-and-versioning-an-ontology/
- https://www.w3.org/TR/owl2-profiles/
- [[ar.a-common-ground-for-virtual-humans]]