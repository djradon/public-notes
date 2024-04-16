---
id: aatezvgrmqvpzzlv06jx5fp
title: Comparing Linked Data Triplestores
desc: ''
updated: 1713245703290
created: 1713245523826
---

-  https://medium.com/wallscope/comparing-linked-data-triplestores-ebfac8c3ad4f


## Highlights

- AllegroGraph takes an extraordinarily long time to populate. Marklogic is overshadowed by AllegroGraph but still takes 2 minutes to load the data in RDF/XML format!
- Stardog does not optimise federated queries adequately.
- Virtuoso has the worst interface.

## Conclusions

* GraphDB for development while you are constructing your application.
* AnzoGraph or Virtuoso when you move into production if speed is important.