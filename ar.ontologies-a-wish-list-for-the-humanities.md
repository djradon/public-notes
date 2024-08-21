---
id: 4kw39mf0ye3zaxv050376sa
title: Ontologies a Wish List for the Humanities
desc: ''
updated: 1724260170322
created: 1724258646377
---

- https://www.academia.edu/50247032/Ontologies_A_Wish_List_for_the_Humanities


## Abstract

In this paper, we analyze the problems the Humanities currently face and discuss how ontologies could help them – provided the ontology toolkits had support for additional capabilities. We enumerate these capabilities and describe their necessity for research in the Humanities.


## Highlights

### Wishlist

#### Wish #1: Ontological Plurality

- ontological toolkits for Humanities research need to be able to deal with a minimum of two ontologies at the same time, namely the mental ontology of the author and the mental ontology of the reader
  - In some sense, textual interpretation is the act of proposing a formal mapping between the mental ontology of the author and the mental ontology of the reader that explains the differences ^h7t5vnihn7ft

#### Wish #2: Contexts

- One way to implement ontological plurality is by supporting contexts, both for ontology building and for reasoning (Guha, 1991)
  - In terms of reasoning, contexts provide a way of compartmentalizing mutually contradictory information without inferring a contradiction
- Contexts provide a straight-forward way to simulate the mental models that researchers construct when they work with texts.
- At a very coarse level, each of the texts and each of the research positions – both own and others – can be assigned their own context and reconstructed autonomously within. 
- Contexts can however be applied in more fine-grained manners, for example to model the individual steps of the reconstructive process.
- By assigning separate contexts to the textual reconstruction, the translation, the analysis of the textual form, the analysis of how the text was edited and the investigations into the traditions and motives leveraged by as well as inspired by the text, the researcher can mix and match possible models for each of these steps simply by bundling contexts
- Furthermore, prior research can be leveraged in equivalent ways, giving a building block quality to the investigation of alternative interpretations.
- Finally, contexts make for handy units of information exchange between researchers who want to collaboratively construct sets of ontologies.
- **In a contextualizing approach, shared assumptions would be factored out and inherited.**
  - Sometimes the additional information augments the inherited information; sometimes more precise restatements override the inherited.
- one important problem to consider is that the beliefs, desires and interpretations are forms of modal statements. That means they do not obey the normal forms of deductive inference
  - for the purposes of historical reconstruction it is important to perform deductive inference on the contents of the beliefs held by the agents under study.
  - The proper way to deal with this distinction is to employ two contexts, one context that captures the beliefs and one context that captures all of the consistent worlds that follow from the contents of the beliefs.

#### Wish #3: Argumentation Systems

- The reconstruction of a text is an argument that assigns meanings to the linguistic elements
- In order to expose such a reconstruction to peer criticism, the argumentative links between the elements have to be made explicit in the ontology
- The ontological toolkits need to support qualifying argumentative links
  - By making the connections between the facts of the arguments obvious, the ramifications of any modifications to the supporting facts become immediately clear as well.
- the assignment of argumentative links between any fact and an interpretation should not be limited to only one link, or even to several links of only one truth value
  - ontology toolkits should provide for a way of enumerating the pro and contra supports for a specific step in the reconstructive argument.

#### Wish #4: Question Corpora Management Systems

- the set of research questions does not remain static: Some questions find answers; new questions are identified; old questions are deemed infertile and placed aside.
- Akin to the way test- and use-cases drive the development of software artifacts, modeling the questions and monitoring the validity of their answer sets can help focus the research effort and ensures that modifications to the theory do not endanger prior gains.
- require the construction of shared repositories of research question sets – akin to the Penn Treebank (Marcus et al, 1993) in natural language processing, the TREC competition 13 in information retrieval or the TTPTP repository (Sutcliffe et al, 1998) in the automatic theorem prover (ATP) community.

#### Wish #5: Representational Expressivity

- supporting contexts entails switching from description or first order predicate logic to modal or higher-order logic – depending on the implementation of the contexts. [^14]
  - This means that “computational completeness (all entailments are guaranteed to be computed) and decidability (all computations will finish in finite time)” – cf. (Smith et al, 2004) – are no longer guaranteed.
  - once incompleteness and undecidability have been incurred – and we believe this step to be unavoidable for the Humanities – one may as well exploit the representational benefits of modal and higher order logic.
  - 
