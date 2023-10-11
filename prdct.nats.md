---
id: iypvlwhcbuwo79fm2uayixf
title: NATS
desc: 'Neural Autonomic Transport System'
updated: 1697039439137
created: 1678139747758
---

- [[c.Software.message-bus]]
- #url https://nats.io/
- [[p.similarTo]] 
- [[p.writtenIn]] #go

## [[c.Host]]

- [[prdct.fly-io]] #free-tier
  - "While the cluster is only accessible from inside the Fly network, you can use Fly's Wireguard support to create a VPN into your Fly organisation and private network."
- 

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