---
id: joiwdd2KjBWzPf68G3vot
title: Fluree
desc: 'Open source semantic graph database that guarantees data integrity, facilitates secure data sharing, and powers connected data insights.'
updated: 1705505342168
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
    - [[c.resource]] https://flur.ee/2019/02/21/time-travel-with-fluree/ https://flur.ee/2021/07/08/time-traveling-with-fluree/
  - " optionally decentralized (e.g. using StorJ via Tardigrade)"
    - [[p.hasSource]] https://github.com/athensresearch/athens/issues/9#issuecomment-786844129
  - [[prdct.json-ld]] support

## Features

- a query peer "runs as an in-memory database peer to the ledger it's subscribed to. But like you mention, it doesn't only need (or need at all) to do so because it's intended to answer Fluree queries from other clients. It could very usefully just subscribe to a ledger in order to monitor data events like newly committed blocks and then to evaluate if that data meets a certain criteria, and--if so--to then trigger some downstream function or additional side effect... the NodeJS peer subscribes to the ledger as a particular cryptographic identity, which means that the listener itself will only be privy to data updates that that identity SHOULD be able to access."

## Learning Resources

- [ ] [Building a Front-End App on Fluree.](https://www.youtube.com/watch?v=USh0-b-f5fo)

## [[c.Resource.Learning]]

- [[ar.fluree.working-with-graph-data]]