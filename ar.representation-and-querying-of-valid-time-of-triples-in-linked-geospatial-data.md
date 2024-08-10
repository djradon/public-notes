---
id: ti4xbs4un4n199v91bdr4lk
title: Representation and Querying of Valid Time of Triples in Linked Geospatial Data
desc: ''
updated: 1723147655378
created: 1720742219876
---

- https://strabon.di.uoa.gr/files/eswc2013.pdf

## Abstract

We introduce the temporal component of the stRDF data model and the stSPARQL query language, which have been recently proposed for the representation and querying of linked geospatial data that changes over time. With this temporal component in place, stSPARQL becomes a very expressive query language for linked geospatial data, go- ing beyond the recent OGC standard GeoSPARQL, which has no support for valid time of triples. We present the implementation of the stSPARQL temporal component in the system Strabon, and study its performance experimentally. Strabon is shown to outperform all the systems it has been compared with.


## Highlights

-  Gutierrez et al. [8, 9] were the first to propose a formal extension of the RDF data model with valid time support. They also introduce the concept of anonymous timestamps in general temporal RDF graphs, i.e., graphs containing quads of the form (s, p, o)[t] where t is a timestamp or an anonymous timestamp x stating that the triple (s, p, o) is valid in some unknown time point x
-  the version of the system Strabon presented in [14], which implements stRDF and stSPARQL, does not implement the temporal dimension of this data model and query language. In this paper we remedy this situation by introducing all the details of the temporal dimension of stRDF and stSPARQL and implementing it in Strabon.
-  With the temporal dimension presented in this paper, stSPARQL also becomes more expressive than the recent OGC standard [[prdct.sparql.geosparql]]
-  we evaluate the performance of our implementation on two large real-world datasets and compare it to three other implementations: (i) a naive implementation based on the native store of Sesame [[prdct.rdf4j]] which we extended with valid time support, (ii) [[prdct.allegrograph]], which, although it does not offer support for valid time of triples explicitly, it allows the definition of time instants and intervals and their location on a time line together with a rich set of func- tions for writing user queries, and (iii) the Prolog-based implementation of the query language AnQL, which is the only available implementation with explicit support for valid time of triples. Our results show that Strabon outperforms all other implementations.
-  values of the datatype strdf:period can be used as objects of a triple to represent user-defined time. In addition, they can be used to represent valid times of temporal triples which are defined as follows.
   -  A temporal triple (quad) is an expression of the form s p o t. where s p o. is an RDF triple and t is a time instant or a time period called the valid time of a triple. An stRDF graph is a set of triples and temporal triples. In other words, some triples in an stRDF graph might not be associated with a valid time.
-  we do not have support (yet) for quantitative temporal constraints in queries (e.g., T1 − T2 ≤ 5).
