---
id: 2330gsyswmwpyg0ivjc37pp
title: HarperDB
desc: 'Unify your application''s code and data to simplify development and scale performance globally'
updated: 1673924883335
created: 1673628242504
---

#baas

#url https://harperdb.io

## [[p.hasLearningResource]]

- https://dev.to/harperdb/using-socketcluster-for-distributed-computing-in-a-unique-way-1cia
  - [[p.hasHighlight]] 
    - So we have our connection, doing full data replication between node 1 and node 2. Making sure we have deterministic data sharing - deciding what data we want to go where. This use case is common for our clients especially in an edge computing scenario: say you have devices in a manufacturing plant collecting temperature data, you really only care when that data goes out of range, so command control wants to know what device is going out of range and what it looks like - then push that data to a separate table and push up to command control - but raw data is sitting only on the edge node and is tailing with time to live - that way we only share the data that really is important to customers.
    - 