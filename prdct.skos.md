---
id: vu2fg1cagr0lewf1yjof656
title: SKOS
desc: 'Simple Knowledge Organization System'
updated: 1715919119914
created: 1706306245897
---

## Description

- designed for representation of thesauri, classification schemes, taxonomies, subject-heading systems, or any other type of structured controlled vocabulary.
- SKOS has been designed to provide a low-cost migration path for porting existing organization systems to the Semantic Web. SKOS also provides a lightweight, intuitive conceptual modeling language for developing and sharing new KOSs. It can be used on its own, or in combination with more-formal languages such as the Web Ontology Language (OWL) [OWL]. SKOS can also be seen as a bridging technology, providing the missing link between the rigorous logical formalism of ontology languages such as OWL and the chaotic, informal and weakly-structured world of Web-based collaboration tools, as exemplified by social tagging applications.


## Topics

### Concept Scheme vs Collection 

- SKOS collections are intended to represent groupings of closely-related concepts within a particular thesaurus.
- Concept Schemes... are intended to capture/identify a single complete thesaurus/taxonomy, which is useful in a situation where several such thesauri/taxonomies co-exist. Items in a ConceptScheme are not necessarily a "grouping" of closely-related terms, but are all part of the same overall hierarchy of terms.

### Intransitive vs Not Transitive

- the SKOS model does not state that skos:broader and skos:narrower are transitive. Yet this does not imply that these properties are intransitive.

### Compositionality and Concept Typing

- start with a common vocabulary for the whole enterprise, but have customizations of it for each line of business... SKOS defines a class called skos:Concept, for any vocabulary concept. Users of SKOS are encouraged to extend SKOS by creating their own subclasses of skos:Concept; each vocabulary will do this in a different way (e.g., defining subdomains in their own vocabularies), while adhering to the basic structure of SKOS.
  - A good example of this is the structure of the [GACS Agricultural Vocabulary](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6751214/), which uses several subclasses of skos:Concept to provide organizational structure to the vocabulary.
    - "GACS Core distinguishes five types of concept: Chemical, Geographical, Organism, Product, and Topic—a minimal set of generic types for exploring the benefits of concept typing before committing to anything more granular."

#### AGROVOC use case

- maintainers re-engineered thesaurus to “fully fledged ontology” but a study of users 6 years later found little support for the use of these custom relation properties.13 In the absence of specific tools and requirements for reasoning, it was unclear to some users what purpose they served.


## Solutions

- [[prdct.skosmos]]

## Examples

- [[prdct.redaktor-vocab]]


## References

- https://medium.com/@dallemang/jug-o-cool-things-i-do-with-rdf-3cdb5b059192
- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6751214/
- https://www.w3.org/TR/skos-primer/
- [[ar.common-slips-in-skos-vocabularies]]
- https://stackoverflow.com/questions/32573812/whats-the-difference-between-skosconceptscheme-and-skoscollection
