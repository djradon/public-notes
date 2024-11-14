---
id: 76k77lkhmabk7paurrd27eb
title: LinkedDataHub
desc: 'collaboratively create and edit RDF ontologies, instance data, and document content enjoying a consistent user experience.'
updated: 1731610992708
created: 1716500096760
---

- https://atomgraph.com/products/linkeddatahub/
- [[c.software.semantic.publishing]] [[c.software.semantic.authoring]] [[c.software.semantic.browser]] [[c.software.visualization.semantic]]
- https://atomgraph.github.io/LinkedDataHub/
- similar: [[prdct.metaphactory]]

## Interesting

- LinkedDataHub is an open source project that has its roots as a Linked Data publishing framework. However, in the 3.x release we are focusing on Linked Data consumption, as **we consider publishing a solved problem** but continue to see a shortage of user-friendly consumption tools.

## default RDF Dataset structure

Default LinkedDataHub dataset structure follows these conventions:

1.  the default graph is not used
2.  each document's description is stored in an RDF named graph whose name is the same as the document URI. The graph can be managed using the [Graph Store Protocol](https://atomgraph.github.io/LinkedDataHub/linkeddatahub/docs/reference/dataset/index.html../http-api/).
3.  documents form a [parent/child hierarchy](https://atomgraph.github.io/LinkedDataHub/linkeddatahub/docs/reference/dataset/index.html../data-management/documents/#hierarchy). There are 2 types of documents: containers that can have other documents as children, and items that cannot.
  

