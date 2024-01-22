---
id: ntoplz1ephb277ktutqibro
title: Temporal
desc: ''
updated: 1705955640038
created: 1674833275685
---

- [[c.Software.Workflow]]
- pronunciation: tem-POR-al
- fork_of: [[prdct.cadence]]
- related: [[prdct.iwf]]

![[prdct.n8n#^xnxaubd7sqiw]]
url: https://temporal.io/

## Features

- time-travel debugging aka [[t.cs.debugging.reverse]]
- [[t.cs.durable-execution]]

## Notes

- uses gRPC for all interprocess communication.

## vs [[prdct.cadence]]

- Temporal allows associating metadata with every payload. It enables features like dynamically pluggable serialization mechanisms, seamless compression, and encryption.
- Temporal supports typescript and python via SDKs

## References

- https://www.youtube.com/watch?v=wIpz4ioK0gI
  - "queues are not a good way to communicate among services when you have complex transactions" @9:34
- https://stackoverflow.com/questions/61157400/temporal-workflow-vs-cadence-workflow