---
id: iypvlwhcbuwo79fm2uayixf
title: NATS
desc: >-
  core messaging capabilities of NATS include pub-sub, request-reply, and queue
  groups.
updated: 1715366521147
created: 1678139747758
---


- [[c.software.messaging.bus]] 
- url: https://nats.io/
- similar: [[prdct.nats]] [[prdct.memphis]] [[prdct.nsq]] ^69m6e1oxkdup
- written-in: #go
- cloud-service: https://www.synadia.com/cloud
- related: [[prdct.walnats]]

## Terms

- A **Leaf Node** extends an existing NATS system of any size, optionally bridging both operator and security domains.
  - Traffic between the leaf node and the cluster assumes the restrictions of the user configuration used to create the leaf connection.
    - Subjects that the user is allowed to publish are exported to the cluster.
    - Subjects the user is allowed to subscribe to, are imported into the leaf node.
  - Leaf nodes appear to the cluster as a single account connection. Leaf nodes can provide continuous NATS service for their clients, even while being temporarily disconnected from the cluster(s). You can even enable JetStream on the leaf nodes in order to create local streams that are mirrored (mirroring is store and forward and therefore can recover from connectivity outages) to global streams in the upstream cluster(s).

## Hosting

- Synadia cloud
- [[prdct.fly-io]] #free-tier
  - "While the cluster is only accessible from inside the Fly network, you can use Fly's Wireguard support to create a VPN into your Fly organisation and private network."

## [[p.hasFeature]]

- three basic communication patterns
  - Publish Subscribe
  - Request/Reply (uses a special "reply subject")
  - Distributed Load Balanced Queue
- [[prdct.nats.jetstream]] for persistence
- [[p.supports]] [[prdct.cloudevents]]
  - https://github.com/cloudevents/spec/blob/main/cloudevents/bindings/nats-protocol-binding.md
- Synadia cloud has an HTTP gateway
  - leverages server-send events (SSE):

## [[p.hasLearningResource]]

- https://natsbyexample.com/