---
id: iypvlwhcbuwo79fm2uayixf
title: NATS
desc: 'core messaging capabilities of NATS include pub-sub, request-reply, and queue groups.'
updated: 1706243170735
created: 1678139747758
---

- [[c.software.message-bus]]
- url: https://nats.io/
- [[p.similarTo]] 
- written-in: #go

## [[c.host]]

- [[prdct.fly-io]] #free-tier
  - "While the cluster is only accessible from inside the Fly network, you can use Fly's Wireguard support to create a VPN into your Fly organisation and private network."
## [[p.hasFeature]]

- three basic communication patterns
  - Publish Subscribe
  - Request/Reply
  - Distributed Load Balanced Queue
- [[prdct.nats.jetstream]] for persistence
- [[p.supports]] [[prdct.cloudevents]]
  - https://github.com/cloudevents/spec/blob/main/cloudevents/bindings/nats-protocol-binding.md

## [[p.hasLearningResource]]

- https://natsbyexample.com/