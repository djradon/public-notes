---
id: 6jwyb2abq6vko2a8rle5zf3
title: Requirements
desc: ''
updated: 1730051810897
created: 1729878881397
---

## IRI minting

- ideally there could be some kind of signature that affirms "the dataset published to this IRI was authorized by a person who has control of the namespace" but I guess its existance at that URL speaks for itself.
- see [[sflow.conv.2024.10.25.semantic-flow-overview#authority]] for approaches to trust

### Dereference Pages

- for [[dereference pages|sflow.concepts.dereference-pages]] you don't want all assertions, only some of the most useful ones, perhaps with links to where you can get more (ie., catalog links)
- mapping of templates to facets, namespaces, datasets, sparql queries

## Canonicalization

- to make diffing easier, all datasets should be canonicalized before commit

## System Time

There are multiple levels of "this data was added, changed, or tombstoned":

### Relator Atoms

### Named Individuals

- the act of using/declaring an IRI itself is a data point. It generates something into existence, even if it doesn't play a role in a relator. And possibly we'll want to be able to issue statements with that IRI that don't use relators. 
- optionally, you can use 

### Version-On-Commit

- see [[sflow.conv.2024.10.25.semantic-flow-overview#i-think-that-releasing-a-new-version-of-any-component-of-a-namespace-requires-a-version-bump-all-the-way-up-the-chain]]

