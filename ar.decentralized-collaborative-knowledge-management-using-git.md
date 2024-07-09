---
id: t6ebsghgw5xwdiku27e1kx7
title: Decentralized Collaborative Knowledge Management Using Git
desc: ''
updated: 1720530822909
created: 1714499726660
---

- https://natanael.arndt.xyz/bib/arndt-n-2018--jws
- keywords: [[prdct.rdf]] [[t.cs.semantic-web]] [[t.km]] [[prdct.quit]]
- similar: [[ar.distributed-collaboration-on-rdf-datasets-using-git]]
- mentions: [[quit]]

## Abstract

The World Wide Web and the Semantic Web are designed as a network of distributed services and datasets. The distributed character of the Web brings manifold collaborative possibilities to interchange data. The commonly adopted collaborative solutions for RDF data are centralized (e. g. SPARQL endpoints and wiki systems). But to support distributed collaboration, a system is needed, that supports divergence of datasets, brings the possibility to conflate diverged states, and allows distributed datasets to be synchronized. In this paper, we present Quit Store, it was inspired by and it builds upon the successful Git system. The approach is based on a formal expression of evolution and consolidation of distributed datasets. During the collaborative curation process, the system automatically versions the RDF dataset and tracks provenance information. It also provides support to branch, merge, and synchronize distributed RDF datasets. The merging process is guarded by specific merge strategies for RDF data. Finally, we use our reference implementation to show overall good performance and demonstrate the practical usability of the system


## Highlights

- Projects from a number of domains are striving for distributed models to collaborate on common knowledge bases. In the domain of e-humanities, the projects Pfarrerbuch3, Catalogus Professorum4 [40], Héloïse – Euro- pean Network on Digital Academic History5 [39], and Pro- fessorial Career Patterns of the Early Modern History6 are good examples of the need to explore and track provenance and the evolution of the domain data.
3http://aksw.org/Projects/Pfarrerbuch
4http://aksw.org/Projects/CatalogusProfessorum
5http://heloisenetwork.eu/
6http://catalogus-professorum.org/projects/pcp-on-web/

-  a system that fosters the evolution of a dataset in a distributed collaborative setup needs to
• support divergence of datasets;
• conflate diverged states of datasets; and
• synchronize different distributed derivatives of the respective dataset.

- creating independent vocabularies (a) in the individual working groups would not help to integrate the datasets. Due to the organizational distribution of the individual research groups, a common vocabulary expressing a mutual agree- ment among the groups (b) can only be the result of a collaborative process

## State of the art

- [[ar.w3.delta-an-ontology-for-the-distribution-of-differences-between-rdf-graphs]]