---
id: iypvlwhcbuwo79fm2uayixf
title: NATS
desc: >-
  core messaging capabilities of NATS include pub-sub, request-reply, and queue
  groups.
updated: 1715631641518
created: 1678139747758
---


- [[c.software.messaging.bus]] 
- url: https://nats.io/
- similar: [[prdct.nats]] [[prdct.memphis]] [[prdct.nsq]] ^69m6e1oxkdup
- written-in: #go
- cloud-service: https://www.synadia.com/cloud
- related: [[prdct.walnats]] [[prdct.benthos]]

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
  - leverages server-send events (SSE)
- embeddable

## Comparison

### Kafka vs NATS

- partitions and topics "makes Kafka highly suited to applications where order matters; for example, state machine replication, event sourcing, log shipping, log aggregation, SEDA (staged event- driven architecture) and CEP (complex event processing)."
- Speaking of topics, the equivalent NATS subject is a lightweight construct that is created automatically based on demand (subscriptions) and is pruned automatically when the demand ceases. NATS subjects are cheap to create, which makes them great for hierarchically organised data, allowing for a fine-grained subscription model.
- (Note: NATS Streaming addresses this, but as stated earlier, it is a different product in its own right.)
- Kafka will never assign a partition to multiple consumers in the same group. So, although Kafka’s load balancing scheme is more coarse-grained than NATS’; it manages to preserve the order of records at the consumer nodes.
- kafka is lightweight

#### Dendrite use case

- "switching to JetStream was transformational. Performance is excellent overall. We make heavy use of the interest-based retention policies to ensure that work is cleaned up when it is complete. We take advantage of being able to manually acknowledge items to ensure they were processed successfully before cleaning up. We’ve been able to successfully manage pools of workers from NATS streams and considerably reduce the amount of complexity in our codebase in a number of places which no longer need their own persistent storage. We’ve even had it successfully running in application-embedded scenarios on iOS and Android as a part of our peer-to-peer demos."

## [[p.hasLearningResource]]

- https://natsbyexample.com/


## References

- https://www.quora.com/What-is-the-difference-between-Apache-Kafka-and-NATS
- https://nats.io/blog/matrix-dendrite-kafka-to-nats/