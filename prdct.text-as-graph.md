---
id: jfuzpajsq4ecsopem0lv8ba
title: Text as Graph
desc: ''
updated: 1680306262840
created: 1680306061571
---

## [[c.Abstract]]

Over the past decades, the question of what text really is has been addressed by a large number of conferences, workshops, articles, and blog posts. If there is one thing that, taken together, those contributions illustrate, it is that our understanding of text is—and has been—constantly in flux and open to many interpretations. Still, there is often a gap between how an editor conceptualizes a source text and how this text is encoded and stored on a computer: using TEI XML, editors are compelled to model their text as a single tree (a hierarchy), whether this structure corresponds with their intellectual understanding or not. Textual features that do not fit naturally into the XML data model require additional layers of code, which hinders processing, querying, and interchange.

The Text-As-Graph (TAG) data model and the associated syntax [[prdct.TAGML]] are developed to express and store textual information as a network. To this end, TAG implements a hypergraph model. In the present contribution, we illustrate the benefits of TAG’s hypergraph for the modeling of features like nonlinearity, discontinuity, and overlap. In contrast to a tree model, a hypergraph accommodates these nonhierarchical structures naturally. By making them part of the data model and the syntax, a TAGML processor can process the features without having to resort to workarounds or schema-aware tools. This lowers the difficulty of working with digital editions and facilitates querying and interchange.

## [[c.Resource.Related]]

- [[ar.texts-as-hypergraphs-an-intuitive-representation-of-interpretations-of-text]]
