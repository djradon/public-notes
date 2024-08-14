---
id: lkkkisrk9liyko1av5yoos2
title: Introducing Ontogen
desc: ''
updated: 1723555426769
created: 1723554355082
---

https://ontogen.io/introduction/part-1

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

