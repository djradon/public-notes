---
id: jfuzpajsq4ecsopem0lv8ba
title: Text as Graph
desc: ''
updated: 1680308322422
created: 1680306061571
---

## [[c.abstract]]

Over the past decades, the question of what text really is has been addressed by a large number of conferences, workshops, articles, and blog posts. If there is one thing that, taken together, those contributions illustrate, it is that our understanding of text is—and has been—constantly in flux and open to many interpretations. Still, there is often a gap between how an editor conceptualizes a source text and how this text is encoded and stored on a computer: using TEI XML, editors are compelled to model their text as a single tree (a hierarchy), whether this structure corresponds with their intellectual understanding or not. Textual features that do not fit naturally into the XML data model require additional layers of code, which hinders processing, querying, and interchange.

The Text-As-Graph (TAG) data model and the associated syntax [[prdct.TAGML]] are developed to express and store textual information as a network. To this end, TAG implements a hypergraph model. In the present contribution, we illustrate the benefits of TAG’s hypergraph for the modeling of features like nonlinearity, discontinuity, and overlap. In contrast to a tree model, a hypergraph accommodates these nonhierarchical structures naturally. By making them part of the data model and the syntax, a TAGML processor can process the features without having to resort to workarounds or schema-aware tools. This lowers the difficulty of working with digital editions and facilitates querying and interchange.

## Summary

- The regular edges in the TAG hypergraph model are directed; the hyperedges are undirected. Nodes in the hypergraph can be connected with either a hyperedge or a regular edge.
- The TAG hypergraph consists of five types of nodes:
  - One Document node. This node serves as the root of the graph. Via a directed edge, the Document node is connected to zero or more Text nodes, Markup nodes, Branching nodes, or Annotation nodes.
  - One or more Text nodes. A Text node contains textual content (UTF-8-encoded), and may be connected to one or more Markup nodes with hyperedges. It is connected to other Text nodes or Branching nodes with directed edges.
  - Zero or more Markup nodes. A Markup node is connected to one or more Text nodes, and has zero or more Annotation nodes.
  - Zero or more Annotation nodes. The Annotation node is connected to one or more Markup nodes or another Annotation node.
  - Zero or more Branching nodes. A Branching node is connected to a Text node or another Branching node with a directed edge. It is used to mark the beginning and end of a nonlinear structure.


## Resources

- [[ar.texts-as-hypergraphs-an-intuitive-representation-of-interpretations-of-text]]
- [[t.cs.graph.hypergraph]]