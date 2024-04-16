---
id: RJuARDM7QgEnTon40cd13
title: GraphDB
desc: ''
updated: 1713246704941
created: 1637954631007
---

- [[c.software.database.graph]]
- [[p.instanceOf]] [[t.cs.data.dbms.graph]]
- written-in: java
- [[p.supports]] [[prdct.rdf-star]]
- produced_by: [[org.ontotext]]
- based_on: [[prdct.rdf4j]]


## Features

- [embeddable](https://graphdb.ontotext.com/documentation/9.8/free/devhub/embeddedgraphdb.html)
- Synchronize data to downstream systems with the Kafka connector.
- can be used with [[prdct.jena]], see https://graphdb.ontotext.com/documentation/9.1/free/using-graphdb-with-jena.html
- [[prdct.sparql.mm]] supports "system time" queries
  - "Note that querying the history log may be slow for big history logs. This is why we recommend using filters to reduce the number of history entries if you have a big repository."

## References

- https://www.ontotext.com/knowledgehub/fundamentals/semantic-repository/