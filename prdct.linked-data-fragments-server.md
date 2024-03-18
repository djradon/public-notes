---
id: 1nged2trp13vnqkx5y3ofhk
title: Linked Data Fragments Server
desc: 'A Triple Pattern Fragments server for Node.js '
updated: 1710803070399
created: 1710803012065
---

- repo: https://github.com/LinkedDataFragments/Server.js
- written_in: javascript (node)

## Motivation

On today's Web, Linked Data is published in different ways, which include [data dumps](http://downloads.dbpedia.org/3.9/en/), [subject pages](http://dbpedia.org/page/Linked_data), and [results of SPARQL queries](http://dbpedia.org/sparql?default-graph-uri=http%3A%2F%2Fdbpedia.org&query=CONSTRUCT+%7B+%3Fp+a+dbpedia-owl%3AArtist+%7D%0D%0AWHERE+%7B+%3Fp+a+dbpedia-owl%3AArtist+%7D&format=text%2Fturtle). We call each such part a [**Linked Data Fragment**](http://linkeddatafragments.org/).

The issue with the current Linked Data Fragments is that they are either so powerful that their servers suffer from low availability rates ([as is the case with SPARQL](http://sw.deri.org/~aidanh/docs/epmonitorISWC.pdf)), or either don't allow efficient querying.

Instead, this server offers [Quad Pattern Fragments](https://linkeddatafragments.org/specification/quad-pattern-fragments/) (a.k.a. **[Triple Pattern Fragments](https://linkeddatafragments.org/specification/triple-pattern-fragments/)**). Each Quad Pattern Fragment offers:

-   **data** that corresponds to a _quad/triple pattern_ _([example](http://data.linkeddatafragments.org/dbpedia?subject=&predicate=rdf%3Atype&object=dbpedia-owl%3ARestaurant))_.
-   **metadata** that consists of the (approximate) total triple count _([example](http://data.linkeddatafragments.org/dbpedia?subject=&predicate=rdf%3Atype&object=))_.
-   **controls** that lead to all other fragments of the same dataset _([example](http://data.linkeddatafragments.org/dbpedia?subject=&predicate=&object=%22John%22%40en))_.

An example server is available at [data.linkeddatafragments.org](http://data.linkeddatafragments.org/).