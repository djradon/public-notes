---
id: n2ln43dertdv5hpgd6lyb4v
title: Event Streaming
desc: 'you need to implement event streaming into your systems to capture, integrate, access, and analyze data in real-time.'
updated: 1715631748118
created: 1674620815689
---

## Highlights

- events constantly push data into our applications. These applications react, blending streams together, building views, changing state, and moving themselves forward. In the streaming model there is no shared database. The database is the event stream, and the application simply molds it into something new.
  - In fairness, streaming systems still have database-like attributes such as tables (for lookups) and transactions (for atomicity), but the approach has a radically different feel, more akin to functional or dataflow languages (and there is much cross-pollination between the streaming and functional programming communities).


## Solutions

- [[prdct.kafka]]
- [[prdct.nats.jetstream]]
- [[prdct.memphis]]

## Comparisons

### Memphis vs Jetstream

- 


## References

- https://pandio.com/event-streams-queues/
- https://pandio.com/what-is-event-streaming-why-is-it-growing-in-popularity/
- https://learning.oreilly.com/library/view/designing-event-driven-systems/9781492038252/ch01.html
- https://thenewstack.io/choosing-between-message-queues-and-event-streams/
- https://docs.memphis.dev/memphis/memphis-broker/comparisons/nats-vs-memphis