---
id: RJuARDM7QgEnTon40cd13
title: GraphDB
desc: ''
updated: 1717220273570
created: 1637954631007
---

- [[c.software.database.graph]]
- [[p.instanceOf]] [[t.cs.data.dbms.graph]]
- written-in: java
- [[p.supports]] [[prdct.rdf-star]] [[prdct.kafka]]
- produced_by: [[org.ontotext]]
- based_on: [[prdct.rdf4j]]
- related: [[prdct.ontotext-platform]]


## Features

- [embeddable](https://graphdb.ontotext.com/documentation/9.8/free/devhub/embeddedgraphdb.html)
- Synchronize data to downstream systems with the Kafka connector.
- can be used with [[prdct.jena]], see https://graphdb.ontotext.com/documentation/9.1/free/using-graphdb-with-jena.html
- [[prdct.sparql.mm]] supports "system time" queries
  - "Note that querying the history log may be slow for big history logs. This is why we recommend using filters to reduce the number of history entries if you have a big repository."
- [[prdct.sparql.geosparql]]
- javascript support allows custom functions
  - could be useful in context of auto-versioning [[ar.star-vers-versioning-and-timestamping-rdf-data-by-means-of-rdf-star-an-approach-based-on-annotated-triples]]
- [spatial extensions](https://graphdb.ontotext.com/documentation/10.6/geo-spatial-extensions.html?highlight=spatial)


## References

- https://www.ontotext.com/knowledgehub/fundamentals/semantic-repository/
- https://ontotext.medium.com/ingesting-data-in-graphdb-using-the-kafka-sink-connector-53036f2e1680