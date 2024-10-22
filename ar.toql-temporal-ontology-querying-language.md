---
id: w4iyn8vjjp4m9uvohd79rfl
title: Toql Temporal Ontology Querying Language
desc: ''
updated: 1729550817115
created: 1729550058837
---

- https://www.researchgate.net/publication/221471747_TOQL_Temporal_Ontology_Querying_Language
- authors: @evdoxios-baratis @euripedes-petrakis @sotiris-batsakis @nikos-maris @nikos-papadakis

## Abstract

We introduce [[TOQL|prdct.toql]], a query language for querying time information in ontologies. TOQL is a high level query language that handles ontologies almost like relational databases. Queries are issued as SQL-like statements involving time (i.e., time points or intervals) or high-level ontology concepts that vary in time. Although indepen- dent from TOQL, this work suggests a mechanism for representing time evolving concepts in ontologies based on the four-dimensional perduran- tist mechanism. However, TOQL prevents users from being familiar with the representation of time in ontologies. To show proof of concept, an ap- plication has been developed that supports translation and execution of TOQL queries on temporal ontologies combined with a reasoning mech- anism based on event calculus. A real world temporal ontology is also implemented on which several TOQL example queries are processed and discussed.

## Highlights

- TOQL handles ontologies almost like relational databases. Queries in TOQL are issued as SQL statements involving time and high-level ontology concepts that (may) vary in time. TOQL maintains the basic structure of an SQL language (SELECT - FROM - WHERE) and treats the classes and the properties of an ontology almost like tables and columns of a database
- TOQL syntax is independent of any temporal representation and can work with any other mechanism (e.g., versioning). As such, the 4D fluent ([[perdurantist|t.phil.perdurantism]]) mechanism is not part of the language and it is not visible to the user (so the user need not be familiar with peculiarities of the underlying mechanism for time information representation)
- In the accompanying implementation, TOQL queries are first translated into equivalent statements in [[SeRQL|prdct.serql]] which are then executed on the underlying OWL temporal ontology. 