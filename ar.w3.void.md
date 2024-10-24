---
id: adkiptp4qp5gak5yfcbw2n5
title: Describing Linked Datasets with the VoID Vocabulary
desc: ''
updated: 1729717652778
created: 1729717652778
---

- https://www.w3.org/TR/void/

## Highlights

### Metadata

#### Root Resources

Many datasets are structured in a tree-like fashion, with one or a few natural “top concepts” or “entry points”, and all other entities reachable from these root resources in a small number of steps.

One or more such root resources can be named using the void:rootResource property. Naming a resource as a root resource implies:

    that it is a central entity of particular importance in the dataset; and
    that the entire dataset can be crawled by resolving the root resource(s) and recursively following links to other URIs in the retrieved RDF responses.

Root resources make good entry points for crawling an RDF dataset.

This property is similar to void:exampleResource. While void:exampleResource names particularly representative or typical resources in the dataset, void:rootResource names particularly important or central resources that make good entry points for navigating the dataset.