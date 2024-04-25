---
id: vm4l9rwu16c839mou641qu7
title: >-
  Star Vers Versioning and Timestamping Rdf Data by Means of Rdf Star an
  Approach Based on Annotated Triples
desc: >-
  What impact a timestamp-based versioning approach used in RDF-star and
  SPARQL-star supporting RDF stores would have on the query & update performance
  and storage costs with different update frequencies, sizes and change ratios
  is what our research aims to find out
updated: 1714073333626
created: 1714065909450
---

- https://www.semantic-web-journal.net/system/files/swj3506.pdf
- https://www.semantic-web-journal.net/content/starvers-versioning-and-timestamping-rdf-data-means-rdf-star-approach-based-annotated
- authors: @filip-kovacevic @fajar-ekaputra @tomasz-miksa @andreas-rauber
- topics: [[prdct.RDF-star]] [[prdct.GraphDB]] [[prdct.jena]] [[prdct.yago.4.5]] [[prdct.rdf3x]]


## Abstract

In the era of data-driven research, we are confronted with the challenge of preserving datasets utilized in experiments for an extended duration. As a result of unretrievable datasets, research cannot be reproduced nor verified. One of the specific challenges is the preservation of the history of evolving datasets. To tackle this challenge, we nowadays use versioning mechanisms on datasets so that each version or revision can be identified. The retrieval of specific versions usually requires queries to be enhanced with some form of version identifiers in order to target specific snapshots. What these version identifiers look like depends on the versioning policy. In timestamp-based policies we would use timestamps in order to retrieve datasets as they were at a specific point in time. The implementation of such policies again depends on the type of data and more importantly on the database system. In the context of RDF data, researchers have contributed with countless temporal RDF models and RDF versioning systems over the last two decades. Many well-known RDF metadata representation models, such as named graphs, reification, n-ary and singletons have simply been applied to represent temporal metadata. However, only little reserach has been done in this direction with one of the more recent RDF extensions with the capability of representing metadata, namely RDF-star. In this paper, we explore the possibilities of RDF-star as basis of a timestamp-based versioning framework. We show how temporal metadata can be represented by utilizing RDF-star's nested triples and stored within RDF-star stores. Moreover, we develop and showcase timestamp-based SPARQL-star templates that can be used to 1) transform RDF datasets into RDF-star datasets 2) update and thereby evolve RDF dtasets and 3) query RDF subsets of time-specific snapshots. We also explain our utilization of the SPARQL query algebra for the purpose of translating SPARQL queries into SPARQL-star queries and link our python-based API that is capable of automatically generating and executing latter queries. Finally, we evaluate our work with datasets and queries from the BEAR benchmark and two RDF stores, namely, Jena TDB2 and GraphDB. Our results suggest that our solution is preferable if the frequency and manner of dataset evolution are uncertain, implying that it outperforms the baseline approaches in sum. However, in cases where datasets are prone to high change rates between consecutive updates our approach does not outperform the baseline approaches in terms of storage consumption. Moreover, the choice of RDF store is significant as the query performance differs vastly between the evaluated RDF-star stores. Our reproducible evaluation process is available on: https://github.com/GreenfishK/starvers_eval


## Highlights

- When it comes
to RDF datasets, we will find three approaches, namely, 1) independent copies (IC) or snapshots 2) change-based
(CB) approaches and 3) timestamp-based (TB) approaches to be the most common ones in the literature
  - IC takes a lot of space
  -  as opposed to the IC paradigm, we have higher reconstruction costs which add up to the retrieval of a specific dataset version. Also, CB apporaches are not nateively supported by SPARQL, i.e. there is no way to retrieve and apply a number of patches to reconstruct a dataset version purely with SPARQL as it is lacking procedural features
  - TB approaches assign timestamps or validity intervals to data on different granularity levels that can range from statement to dataset level so that a dataset can be retrieved as it was at a certain point in time
    - by implementing clever temporal indexes
and partitioning methods we can achieve fast retrievals that add only little query performance overhead compared
to querying isolated snapshots directly


### Versioning

- [[prdct.rdf3x]] approach to continuous validity is to leave out the deletion timestamp for the most recent version of the triple, which is different from our approach 
  - Another difference to our approach is that their solution is built for RDBMS systems and not for RDF stores

## SQT Limitations

- As long as each data triple has only one time interval, i.e. only one pair of the previously mentioned temporal properties, this model is solid for representing temporal metadata about facts
  - with the SQT-based representation, distinguishing which quoted triples belong together, i.e. form a pair, becomes problematic.

## NQT-SP temporal metadata representation model

A triple can be annotated with our two temporal properties using the NQT-SP pattern as follows:

`<< << tr1 >> vers:valid_from t1 >> vers:valid_until tE .`

If we replay the same scenario as in the previous section, just with the new pattern, we get following dataset:

```
nqtsp1: << << tr1 >> vers:valid_from t1 >> vers:valid_until t2 .
nqtsp2: << << tr1 >> vers:valid_from t3 >> vers:valid_until tE .
```

### Property Path issues

- Our approach, however, reaches its limit when it 