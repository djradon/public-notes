---
id: c9bd6fqywmiw0ndy7ufx1f0
title: Ldkit
desc: 'Linked Data query toolkit for TypeScript developers provides ORM-like abstraction over RDF datasources'
updated: 1731616522458
created: 1717524050580
---

- https://ldkit.io/
- repo: https://github.com/karelklima/ldkit
- compatible-with: [[prdct.comunica]] [[prdct.deno]] [[prdct.node]]

## Concepts

### Query Engine

LDkit ships with a simple SPARQL query engine that lets you execute queries over a SPARQL endpoint. This engine is used by default, unless you specify a custom one.

If you want to query other RDF data sources like files or in-memory quad stores, you need to use a custom query engine like Comunica, or implement your own.


## References

- https://ldkit.io/docs/components/query-engine