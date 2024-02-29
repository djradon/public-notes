---
id: cQHSPbwz5JLE40UxftY7w
title: RDF
desc: resource description format
updated: 1709141879153
created: 1633160681527
---



- [[p.instanceOf]] [[c.specification]]

## to do

- [-] [[p.summarized]] [RDF datasets](https://www.w3.org/TR/rdf11-datasets/)
  - the concept of the "unnamed default graph"/master-graph is interesting; 
    - seems like dendron.yml is the master graph. expre
  - [[c.resource]] [The unnamed/default graph should have a standard name](https://github.com/w3c/sparql-12/issues/43)

## [[p.hasIssue]]

- contrary to [some claims](https://www.ontotext.com/knowledgehub/fundamentals/what-is-rdf/), RDF and OWL are not fluent, at least compared to GraphDown
- calls verbs properties / predicates
- confuses properties and predicates
- can't easily express intransitive relations (properties)
- [[Resources That Refer Vs Resources That Are|vs.resources-that-refer-vs-resources-that-are]] 
  - aka "indicator vs subject"
- [punning](https://www.w3.org/2007/OWL/wiki/Punning): also a solution
  - @chatgpt.4: 
    - **Class-Individual Punning**: This is where the same URI is used to denote a class in one context and an individual in another. For example, you might have a class `:Person` and also use `:Person` as an individual to represent the generic concept of a person. In RDF and OWL, this is legal because classes in OWL are also individuals in the sense of RDF.
    - **Class-Property Punning**: Similarly, the same URI can be used to denote a class in one context and a property in another. This can be useful for modeling certain kinds of relationships in a more flexible way.

### temporal problems

- see [[ar.a-temporal-rdf-model-for-multi-grained-time-information-modeling]]
- https://blog.iandavis.com/2009/08/representing-time-in-rdf-part-1/
- [Temporal RDF](http://www.dcc.uchile.cl/~cgutierr/papers/temporalRDF.pdf) introduces a fourth time component to the triple. 


## can be expressed as 

- [[prdct.rdf.aref]]
- [[prdct.rdf.turtle]]

## Solutions

- [[prdct.rdfsharp]]
- [[prdct.bitrdf]]

## Resources

- https://www.w3.org/TR/rdf11-datasets/
  - [[p.begsQuestion]] [-] What is [[the difference betwee the union of the graphs and their merge|tasks.rdf.the-difference-betwee-the-union-of-the-graphs-and-their-merge]]? Is the distinction meaningful for [[prdct.dendron]]?
- https://www.w3.org/TR/rdf-concepts
- https://www.w3.org/TR/rdf-schema/
- [Predefined Namespace Prefixes](https://www.orpha.net/sparql?nsdecl)

### [[p.hasLearningResource]]

- https://www.w3.org/TR/rdf11-primer/
- https://open.hpi.de/

### [[p.hasWishList]]

- https://lists.w3.org/Archives/Public/semantic-web/2009Nov/0040.html

