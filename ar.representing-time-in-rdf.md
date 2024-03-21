---
id: 3shosjiu5pdogqrx1zf182k
title: Representing Time in Rdf
desc: ''
updated: 1711032342404
created: 1711032342404
---

- url:
  - https://blog.iandavis.com/2009/08/representing-time-in-rdf-part-1/
  - https://blog.iandavis.com/2009/08/representing-time-in-rdf-part-2/

## Approaches

### Approach 1: Conditions and Time Slices

Conditions were my invention to model the state of being of an individual at a point in time. They are basically time slices as used in OpenCyc (the original CYC notion of subAbstractions seems to be missing from OpenCyc).

### Approach 2: Named Graphs

physically divide my data up into separate graphs. Each graph contains triples that hold true for a specified time interval. One graph is designated as holding the time interval information for all the other graphs.

### Approach 3: Reified Relations

I reify every triple that is time-dependent. That means every triple is split out into its constituent parts which will obviously lead to an explosion of triples.

### Approach 4: N-ary Relations

a new class is created for each time-dependent predicate. This new class represents the context of the property and allows more specific predicates to be used that provide extra meaning.

## Conclusions

### Approach 1: Conditions and Time Slices

This approach seems very workable and there is a large body of philosophical work pertaining to this view of the world. In RDF terms though, there seems to be a problem with the domains of properties. Using the properties as I have done here implies that the "conditions" are both intervals of time and real-world things which seems awkward to me. I could separate the time intervals into new resources linked to the conditions with some kind of "existed during" predicate. This would complicate things a little, but perhaps not too greatly.


### Approach 2: Named Graphs

Named graphs appear to partition the data very nicely. However it seems that they don't make the querying any simpler. If it were possible to define a merge of all possible graphs that cover the time interval of interest and query that directly then it could be possible to write very natural queries and completely ignore the time component. This could be possible with a two-phase approach to running the queries or perhaps SPARQL sub-queries might help.

The main problem with named graphs is that they lie outside of the standard RDF model. In fact they are only really formalised by the SPARQL specification. There are no standardised serialisations for named graph data so it is not generally possible to query a SPARQL service and retrieve the named graph information. The TRIG and TRIX serialisations do support named graphs but they are not widely implemented in comparison to RDF/XML, Turtle or Ntriples, none of which support anything beyond the standard RDF model. I don't know of any reasoners that can work across multiple named graphs like this either.

### Approach 3: Reified Triples 

Approach 3 avoids the domain and range problem experienced by Approach 1 where the conditions were being used with properties whose domains were foaf:Agents. In Approach 3, properties are used with the appropriate resource types when they are timeless and never actually asserted when they are time-dependent. However, this approach is tedious for large quantities of data. The semantics are all locked away behind the reified triples. Once again I don't know of any reasoners that could work with this kind of data.


### Approach 4: N-ary Relations

in the examples shown here Approach 4 is identical to Approach 3 in complexity. In fact the key difference is the use of rdf:type rather than ex:property to distinguish the different types of relationships. In this respect it seems to offer no advantage over Approach 3 and adds the complexity of specific property names for each context relationship.

However, it does potentially offer a wider use beyond simply recording time-varying properties. A context could include other factors such as provenance or location. Also it could be easier to model multi-agent contexts such as a marriages with predicates to represent the bride and groom separately.



## References

-   [Refactoring BIO with Einstein Part 1: First Steps](http://blog.iandavis.com/2005/04/refactoring-bio-with-einstein-part-1-first-steps) — my first post that touches on modelling of time in genealogy. At this point I was attempting to model it simply using an event model, i.e. a sequence of things that happen to people and places.
-   [Refactoring BIO with Einstein Part 2: Conditions](http://blog.iandavis.com/2005/10/refactoring-bio-with-einstein-part-2-conditions) — this is the post in which I first introduced Conditions (i.e. Approach 1). The post uses almost exactly the same example as Scenario 1.
-   [Refactoring Bio With Einstein Part 3: Temporal Invariants](http://blog.iandavis.com/2006/03/refactoring-bio-with-einstein-part-3-temporal-invariants) — in the third part of the series I explored those properties of a person that are timeless, or "temporally invariant".
-   [Refactoring BIO with Einstein Part 4: Employment and Families](http://blog.iandavis.com/2006/03/refactoring-bio-with-einstein-part-4-employment-and-families) — in this post I continue the theme of part 2 and demonstrate how employment periods could be described using conditions and events that mark transitions between conditions.
-   [Temporal Scope for RDF Triples](http://www.jenitennison.com/blog/node/101) — in this blog post Jeni Tennison describes her attempts to model time for the London Gazette data she is working with. She describes the reified approach (Approach 3) as unacceptable because most triple stores do not deal with reified data (i.e. don't allow you to query it in its un-reified form). She describes two acceptable approaches which are N-ary relationships (Approach 4) and named graphs (Approach 2) with a preference for the latter. Some useful comments point to other examples of these approaches.
-   [RDF and the Time Dimension Part 1](http://oxforderewhon.wordpress.com/2008/11/28/rdf-and-the-time-dimension-part-1/) — in this post the author explains succinctly where the problem lies although the example used is flawed because it contains hidden context (i.e. "August is a summer month..." is not true in general and needs the context "...for those in the Northern Hemisphere", which can be modelled in RDF). The post also settles on named graphs as a solution but claims they cannot be used for continuous dimensions such as time (missing the solution of using something like OWL-Time to represent intervals and relative timings).
-   [RDF and the Time Dimension Part 2](http://oxforderewhon.wordpress.com/2008/12/10/rdf-and-the-time-dimension-part-2/) — in this follow-up post the author proposes reifying statements and adding a new predicate to relate the reified statement to the context. (A hybrid of Approach 3 and Approach 4?). A second and preferred solution using named graphs is also presented. The author also demonstrates how to obtain a snapshot of all triples that held true at a specific time under both approaches (a "snapshot").
-   [OWL Time](http://www.w3.org/TR/owl-time/) — an ontology of time concepts
-   [Property Reification Vocabulary](http://esw.w3.org/topic/PropertyReificationVocabulary) — a proposal for mapping between reified properties and classes that represent the reifications (i.e. between Approach 3 and Approach 4)
-   [Temporal RDF](http://www.dcc.uchile.cl/~cgutierr/papers/temporalRDF.pdf)
-   [Music Ontology Events](http://motools.sourceforge.net/event/event.html)