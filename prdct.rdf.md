---
id: cQHSPbwz5JLE40UxftY7w
title: RDF
desc: resource description format
updated: 1715895316135
created: 1633160681527
---

- related: [[prdct.rdf-processing-toolkit]] [[prdct.spin]]
- [[p.instanceOf]] [[c.specification]]



## Features

- Blank (or anonymous) nodes are RDF resources with identifiers that exist only locally. In other words, their identifiers are not URLs. They are sometimes also called anonymous nodes. They make life easier for data producers, who can easily create (nested) resources without having to mint all the URLs. In most non-RDF data models, blank nodes are the default. For example, we nest JSON object without thinking twice.

## Datasets

- An RDF dataset is a collection of RDF graphs, and comprises:

  - Exactly one default graph, being an RDF graph. The default graph does not have a name and MAY be empty.
  - Zero or more named graphs. Each named graph is a pair consisting of an IRI or a blank node (the graph name), and an RDF graph. Graph names are unique within an RDF dataset.
- "We informally use the term RDF source to refer to a persistent yet mutable source or container of RDF graphs."

### Dataset Thoughts

- [-] [[p.summarized]] [RDF datasets](https://www.w3.org/TR/rdf11-datasets/)
  - the concept of the "unnamed default graph"/master-graph is interesting; 
    - [[c.resource]] [The unnamed/default graph should have a standard name](https://github.com/w3c/sparql-12/issues/43)

## Typed Literals

- RDF does not place any limits on what datatypes might be associated with a literal. The model recommends using a standard type library, like XML Schema, wherever possible but the only real constraint is that datatypes should be identified by a URI. Creating a new URI for an application or domain specific datatype allows the type system to be easily extended. The datatype URI can be annotated with additional RDF statements, e.g. a label or description, to describe its usage.
- The key limitation to custom datatypes is that SPARQL query engines will not understand how to compare values of that type. Some SPARQL query processors may provide support for understanding the range of types it understands.
- Note that a typed literal with a custom datatype can also be modelled as a sub-property.
  - Advantages
    - Simpler querying of data by allowing the use of triple patterns, rather than FILTERs for extracting data of a common type.
    - More explicit, fine-grained semantics
  - Disadvantages
    - Increases the number of very similar properties, requiring redundancy of data or reasoning to allow applications to treat them generically
    - Doesn't address the core requirement to indicate the lexical form of a structured value
- Recommendation:
  - Use a custom datatype to label particular types of structured value that share a common lexical form. These values may be associated with a broad range of different properties. Processing applications may want to implement a common set of type conversions or display options for the values.
  - Use a sub-property in all other cases

## Highlights

- the property "a" is used to indicate the "type" or "class" of a resource. It is a shorthand notation for the "rdf:type" predicate.


## [[p.hasIssue]]

- [ordering](https://ontola.io/blog/ordered-data-in-rdf), although maybe [[prdct.hydra]] collections could help
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
- [Temporal RDF](http://www.dcc.uchile.cl/~cgutierr/papers/temporalRDF.pdf) introduces a fourth time component to the triple. "I chose not to cover this approach in a lot of detail because it extends the RDF model in a way that no current triple store implements"

### Ordering

There are no arrays in RDF, and don't use the order in which serialized triples appear.

RDF Containers:

- Come in three forms: rdf:Seq (ordered), rdf:Bag (unordered), rdf:Alt (alternatives with default)
- You can add new items by simply adding RDF triples
- Inserting items is hard: requires rewriting many statements
- Must be stored in a single graph / machine / server (centralized)
- Have a formally unknown ending (open world assumption)

RDF Collections:

- An ordered chain of rdf:List resources
- You have to edit / remove statements before you can add new items
- Inserting items is easy: requires changing just a few statements
- Can span many graphs / machines / servers (decentralized)
- Have a known ending (the rdf:nil)
  
Pagination:

- Use ActivityStreams collections

Converting to arrays:

- Use a library, such as @rdfdev/collections


## Abstract Model


### 1.5 RDF and Change over Time

The RDF data model is atemporal: RDF graphs are static snapshots of information.

However, RDF graphs can express information about events and about temporal aspects of other entities, given appropriate vocabulary terms.

Since RDF graphs are defined as mathematical sets, adding or removing triples from an RDF graph yields a different RDF graph.

We informally use the term RDF source to refer to a persistent yet mutable source or container of RDF graphs. An RDF source is a resource that may be said to have a state that can change over time. A snapshot of the state can be expressed as an RDF graph. For example, any web document that has an RDF-bearing representation may be considered an RDF source. Like all resources, RDF sources may be named with IRIs and therefore described in other RDF graphs.

Intuitively speaking, changes in the universe of discourse can be reflected in the following ways:

  - An IRI, once minted, should never change its intended referent. (See URI persistence [WEBARCH].)
  - Literals, by design, are constants and never change their value.
  - A relationship that holds between two resources at one time may not hold at another time.
  - RDF sources may change their state over time. That is, they may provide different RDF graphs at different times.
  - Some RDF sources may, however, be immutable snapshots of another RDF source, archiving its state at some point in time.




## can be expressed as 

- [[prdct.rdf.aref]]
- [[prdct.rdf.turtle]]
- [[prdct.hextuples]]
- [[prdct.json-ad]]
- [[prdct.JSON-LD]]

## Solutions

- [[prdct.rdfsharp]]
- [[prdct.bitrdf]]

## Resources

- https://www.w3.org/TR/rdf11-datasets/
  - [[p.begsQuestion]] [-] What is [[the difference betwee the union of the graphs and their merge|tasks.rdf.the-difference-betwee-the-union-of-the-graphs-and-their-merge]]? Is the distinction meaningful for [[prdct.dendron]]?
- https://www.w3.org/TR/rdf-concepts
- https://www.w3.org/TR/rdf-schema/
- [Predefined Namespace Prefixes](https://www.orpha.net/sparql?nsdecl)
- https://ontola.io/blog/rdf-serialization-formats
  - mentions [[prdct.json-ad]]

### [[p.hasLearningResource]]

- https://www.w3.org/TR/rdf11-primer/
- https://open.hpi.de/

### [[p.hasWishList]]

- https://lists.w3.org/Archives/Public/semantic-web/2009Nov/0040.html

## References

https://patterns.dataincubator.org/book/custom-datatype.html