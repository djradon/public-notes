---
id: 0kwo3pj00n4rwrs1y4ossod
title: Linked Data Fragments
desc: 'Query the Web of data on Web-scale by moving intelligence from servers to clients.'
updated: 1715716817493
created: 1714581302764
---

- https://linkeddatafragments.org/
- related: [[prdct.comunica]]

## Description

- each **type**(?) of linked data fragment (including triple pattern fragments) is defined by
  - data
  - metadata
  - controls (how to access more data)

## Examples

- data dumps (example): their selector is the universal selector, their metadata set includes the file size, and their control set is empty.

- subject pages (example): their selector is a subject URI, their metadata set is often empty, and their control set is given by URIs that can be dereferenced.

- SPARQL results (example): their selector is a CONSTRUCT query, their metadata set is empty, and their control set includes the endpoint URI, which allows to retrieve other SPARQL results.



## References

- https://videolectures.net/iswc2014_verborgh_querying_datasets/