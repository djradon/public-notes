---
id: joiwdd2KjBWzPf68G3vot
title: Fluree
desc: 'Open source immutable semantic graph database that guarantees data integrity, facilitates secure data sharing, and powers connected data insights.'
updated: 1710563577133
created: 1634617777670
---

supports: 
  - type: storage
    products: ["[[prdct.ipfs]]", "[[prdct.aws.s3]]"]
  - type: data_format
    products: prdct.json-ld

- [[c.software.database.graph]] [[c.software.database.graph.rdf]]
- written-in: #clojure JVM!
- [[p.hasApplication]] [[t.km]]
- [[p.hasBlog]] https://flur.ee/blog/
- [[p.hasFeature]] 
  - [[t.cs.data.time-travel]]
    - [[c.resource]] https://flur.ee/2019/02/21/time-travel-with-fluree/ x
  - " optionally decentralized (e.g. using StorJ via Tardigrade)"
    - [[p.hasSource]] https://github.com/athensresearch/athens/issues/9#issuecomment-786844129
  - [[prdct.json-ld]] support

## Features

- a query peer "runs as an in-memory database peer to the ledger it's subscribed to. But like you mention, it doesn't only need (or need at all) to do so because it's intended to answer Fluree queries from other clients. It could very usefully just subscribe to a ledger in order to monitor data events like newly committed blocks and then to evaluate if that data meets a certain criteria, and--if so--to then trigger some downstream function or additional side effect... the NodeJS peer subscribes to the ledger as a particular cryptographic identity, which means that the listener itself will only be privy to data updates that that identity SHOULD be able to access."
- "can be embedded inside of your applications (Clojure, NodeJS for now)"
- [Time and Immutability in Data Systems](https://www.youtube.com/watch?v=CLZm3ZjvQqM&t=1972s)... probably only for clock-time, natively.  
- inferencing (e.g., equivalent properties, but that's only useful if you're using data from different ontologies; okay, it's just useful, period) and 
  - Aliasing makes it possible to not only find equivalent data, but return it in the terms that are useful to us.
- Objects: you can further describe the subgraph you want to build by including nested objects. Our dataset doesn't actually include any data with multiple layers of connections
- History Queries: also powered by immutability, but are preformed differently than time-travel queries. While time-travel allows users to view the ledger from different points in history, history queries capture each of the data state changes that effected a given entity up until the present moment.

## Use Cases

- A particular use case around user-specific ledgers, where each user has their own ledger, would demonstrate this perfectly. Given the ability to run database/query peers directly off of an individual ledger, this would also allow ledger-specific users to efficiently build their own applications off their own database peers without any of the security complexities of establishing a downstream peer to a multi-tenant ledger

## Learning Resources

- [ ] [Building a Front-End App on Fluree.](https://www.youtube.com/watch?v=USh0-b-f5fo)

## [[c.Resource.Learning]]

- [[ar.fluree.working-with-graph-data]]

## References

- https://next.developers.flur.ee/docs/learn/guides/working-with-ontologies/