---
id: 4c9zzrqiu7zdop7dvar1iyz
title: Voidext
desc: ''
updated: 1753130129196
created: 1753129827526
---

- https://biosoda.expasy.org/voidext/

## Summary

To enhance semantic interoperability at the data level and to facilitate the understanding of how multiple datasets can be related and queried, we hereby extended the existing Vocabulary of Interlinked Datasets (VoID). VoID is an RDF Schema vocabulary used to describe metadata about RDF datasets such as structural metadata, access metadata and links between datasets. However, VoID is quite limited in what concerns providing terms and patterns to describe semantic relations between datasets. To mitigate this problem, we introduce the concept of virtual link set. A virtual link is an intersection data point between two RDF datasets. A data point is any node or resource in an RDF graph such as literals and IRIs (Internationalized Resource Identifier). The links are required in order to understand how to semantically relate datasets and, for instance, to enable performing SPARQL federated queries, given that they act as joint points between the federated sources.