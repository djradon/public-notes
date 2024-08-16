---
id: lkkkisrk9liyko1av5yoos2
title: Introducing Ontogen
desc: ''
updated: 1723824464001
created: 1723554355082
---

- https://ontogen.io/introduction/part-1, https://ontogen.io/introduction/part-2, 

## Highlights

### Source Control Management vs. Data Control ManagementPermalink

- Roles: In an SCM, the committer is the crucial role. While SCMs recognize the difference between author and committer, in practice, this is usually of little importance. For a dataset, however, authorship, i.e., the exact source of datasets, is of greater importance, and many other roles are relevant and should be differentiable, such as data processors (people or systems that transform, clean, or enrich raw data), data curators (experts who organize, categorize, and enrich data with metadata), data protection officers, etc.
-   Lack of metadata: Datasets often require extensive metadata (e.g., origin, license, timestamps) that are not natively supported in SCMs.
-   Granularity of changes: SCMs often work at the file level, while for datasets, individual records or fields may be relevant.
-   Database integration: DCMs should ideally be able to interact directly with database systems, which is not provided for in SCMs.

### Problems with previous versioning systems for rdf

- The main problem with named graphs for versioning is that parts of a graph simply cannot be addressed directly.
  - This forces us to create a separate named graph for every small group of triples we want to version, which can quickly lead to a flood of graphs and thus an unwieldy RDF dataset.
  - This becomes particularly problematic when working with different named graphs for content purposes, which then become difficult to distinguish among this flood.
- With RDF-star, "it is now trivial to define virtual, URI-identifiable sets of statements, i.e., partial graphs within a graph" by assigning the statement to a common resource using a property.

### RTC

published the [[prdct.rdf-triple-compounds]] (RTC) vocabulary last year

## RDF Speech Acts

- An og:SpeechAct represents a very specific form of speech act: the utterance of RDF statements or modification.
  - allows us to capture not just the content of RDF data, but also the act of asserting or changing that data, along with all the contextual information that surrounds that act.
  - an action that does not represent the actual addition or modification of the dataset (we will continue to call this action a commit, following the usual versioning terminology)
  - Instead, it represents the act of the original utterance of the statements in this dataset or subsequent acts that supplement, revise, confirm, etc. the original statements. 
    - This is because the central questions of provenance, i.e., the origin of the data, revolve around these acts.
- our aim is to provide a model that allows us to capture information related to all possible questions about these utterances and record them as metadata.
- we don’t need to develop a new ontology from scratch to model these metadata. There is already an excellent and standardized basis: the [[prdct.prov-o]] vocabulary
- we define our og:SpeechActs as a special manifestation, i.e., a subclass of prov:Activity
  - allows us to leverage the extensive semantics of the PROV vocabulary while modelling our specific concept of speech acts for RDF data.

## References

- https://ontogen.io/introduction/part-2