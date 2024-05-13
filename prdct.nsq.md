---
id: 2ejtyqvsautes0flkx7kpgs
title: NSQ
desc: realtime distributed messaging platform
updated: 1714592388393
created: 1714591824008
---

- https://nsq.io/
- repo: https://github.com/nsqio/nsq
- written-in
- supports: go javascript python
![[prdct.nats#^69m6e1oxkdup]]


## Features

-   support distributed topologies with no SPOF
-   horizontally scalable (no brokers, seamlessly add more nodes to the cluster)
-   low-latency push based message delivery ([performance](https://nsq.io/overview/performance.html))
-   combination load-balanced _and_ multicast style message routing
-   excel at both streaming (high-throughput) and job oriented (low-throughput) workloads
-   primarily in-memory (beyond a high-water mark messages are transparently kept on disk)
-   runtime discovery service for consumers to find producers ([nsqlookupd](https://github.com/nsqio/nsq/tree/master/nsqlookupd/README.md))
-   transport layer security (TLS)
-   data format agnostic
-   few dependencies (easy to deploy) and a sane, bounded, default configuration
-   simple TCP protocol supporting client libraries in any language
-   HTTP interface for stats, admin actions, and producers (_no client library needed to publish_)
-   integrates with [statsd](https://github.com/etsy/statsd/) for realtime instrumentation
-   robust cluster administration interface ([nsqadmin](https://github.com/nsqio/nsq/tree/master/nsqadmin/README.md))
- durability: "primarily an in-memory messaging platform"

## References

https://github.com/centrifugal/centrifugo/issues/45