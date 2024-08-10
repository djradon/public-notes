---
id: sjb3dggv4an4h7dc1rhj6e8
title: XTDB V2
desc: ''
updated: 1722895924311
created: 1705967884143
---


- docs: https://docs.xtdb.com/

## vs xtdb

- "Where XTDB has previously been optimized for point-in-time historical queries, v2 now supports ‘cross-time’ queries, e.g. temporal joins and temporal range scans. This unlocks the complete history of data for rich analysis."

## Features

### Full Bitemporal

- bitemporal support (point-in-time querying and full bi-[[t.cs.graph.temporal-joins]]
)
  - "Where XTDB has previously been optimized for point-in-time historical queries, v2 now supports ‘cross-time’ queries, e.g. temporal joins and temporal range scans. This unlocks the complete history of data for rich analysis.
  - We support the SQL:2011 standard for bitemporal functionality, and it’s built into the heart of XTQL too."

- "XTDB 2 will compute and maintain incremental indexes on-the-fly based on the raw data, so index updates will present far less operational impact. This also means the transaction log is now ~ephemeral in the new architecture (no more event-sourcing-style replays required, ever)."
