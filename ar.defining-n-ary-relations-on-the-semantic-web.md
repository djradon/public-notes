---
id: tq4knxb7t4ln11ktfuwiye3
title: Defining N-ary Relations on the Semantic Web
desc: ''
updated: 1729505641422
created: 1729505155337
---

- https://www.w3.org/TR/swbp-n-aryRelations/
- authors: @natasha-noy @alan-rector @pat-hayes @christopher-welty
- related: [[ar.representing-classes-as-property-values-on-the-semantic-web]]

## Abstract

In Semantic Web languages, such as RDF and OWL, a property is a binary relation: it is used to link two individuals or an individual and a value. However, in some cases, the natural and convenient way to represent certain concepts is to use relations to link an individual to more than just one individual or value. These relations are called n-ary relations. For example, we may want to represent properties of a relation, such as our certainty about it, severity or strength of a relation, relevance of a relation, and so on. Another example is representing relations among multiple individuals, such as a buyer, a seller, and an object that was bought when describing a purchase of a book. This document presents ontology patterns for representing n-ary relations in RDF and OWL and discusses what users must consider when choosing these patterns.

## Highlights

Issue 1: If property instances can link only two individuals, how do we deal with cases where we need to describe the instances of relations, such as its certainty, strength, etc?

Issue 2: If instances of properties can link only two individuals, how do we represent relations among more than two individuals? ("n-ary relations")

Issue 3: If instances of properties can link only two individuals, how do we represent relations in which one of the participants is an ordered list of individuals rather than a single individual?

### 