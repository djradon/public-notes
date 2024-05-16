---
id: vu2fg1cagr0lewf1yjof656
title: SKOS
desc: 'Simple Knowledge Organization System'
updated: 1715893063830
created: 1706306245897
---

- designed for representation of thesauri, classification schemes, taxonomies, subject-heading systems, or any other type of structured controlled vocabulary.

## Topics

### Concept Scheme vs Collection 

- SKOS collections are intended to represent groupings of closely-related concepts within a particular thesaurus.
- Concept Schemes... are intended to capture/identify a single complete thesaurus/taxonomy, which is useful in a situation where several such thesauri/taxonomies co-exist. Items in a ConceptScheme are not necessarily a "grouping" of closely-related terms, but are all part of the same overall hierarchy of terms.

### Intransitive vs Not Transitive

- the SKOS model does not state that skos:broader and skos:narrower are transitive. Yet this does not imply that these properties are intransitive.

## Solutions

- [[prdct.skosmos]]

## Examples

- [[prdct.redaktor-vocab]]

## References

- https://www.w3.org/TR/skos-primer/
- [[ar.common-slips-in-skos-vocabularies]]
- https://stackoverflow.com/questions/32573812/whats-the-difference-between-skosconceptscheme-and-skoscollection