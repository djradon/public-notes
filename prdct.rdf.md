---
id: cQHSPbwz5JLE40UxftY7w
title: RDF
desc: resource description format
updated: 1698704342168
created: 1633160681527
---


- [[p.instanceOf]] [[c.Specification]]

## to do

- [-] [[p.summarized]] [RDF datasets](https://www.w3.org/TR/rdf11-datasets/)
  - the concept of the "unnamed default graph"/master-graph is interesting; 
    - seems like dendron.yml is the master graph. expressed as yaml
  - [[c.Resource]] [The unnamed/default graph should have a standard name](https://github.com/w3c/sparql-12/issues/43)

## [[p.hasIssue]]

- contrary to [some claims](https://www.ontotext.com/knowledgehub/fundamentals/what-is-rdf/), RDF and OWL are not fluent, at least compared to GraphDown
- calls verbs properties / predicates
- confuses properties and predicates
- can't easily express intransitive relations (properties)

### temporal problems

- see [[ar.a-temporal-rdf-model-for-multi-grained-time-information-modeling]]
- https://blog.iandavis.com/2009/08/representing-time-in-rdf-part-1/
- [Temporal RDF](http://www.dcc.uchile.cl/~cgutierr/papers/temporalRDF.pdf) introduces a fourth time component to the triple. I chose not to cover this approach in a lot of detail because it extends the RDF model in a way that no current triple store implements and it requires a numeric time to be associated with each triple, preventing relative times from being expressed.
## can be expressed as 

- [[prdct.rdf.aREF]]
- [[prdct.rdf.turtle]]
 
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
