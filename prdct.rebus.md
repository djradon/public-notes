---
id: e3472xdc0i3144yqep7qwp6
title: Rebus
desc: 'Simple and lean service bus implementation for .NET '
updated: 1707851953369
created: 1707692299145
---

- repo: https://github.com/rebus-org/Rebus
- similar_to: [[prdct.masstransit]]
- supports
  - message bus: 

## Cons

- does not lend itself very well to the streaming nature of event brokers like NATS Streaming and Kafka – I think Topos is a better fit for that.

## Questions

- @dave: I'm so curious why Rebus does not lend itself to the streaming nature of some event brokers.

Messaging with streams is just different from messaging with queues.

Queues generally have the property that a message can be consumed by one recipient only, and then it gets ACKed (i.e. deleted from the queue). Event streams generally have the property that they can be read, sequentially, by any number of clients, all of whom simply keep track of how far they have come.

When consuming messages from queues, you generally can't make too many assumptions about the ORDER of messages, ESPECIALLY if a message could potentially be a re-delivered message that has been sitting in a dead-letter queue for a while. OTOH when working with log-based brokers, you CAN make assumptions about ordering, as messages withing a given partition of a specific topic will be ordered.

The properties mentioned so far probably is the explanation why messages from queues tend to model isolated items of work, whereas messages in streams generally tend to be connected to their "neighbors" (i.e. must be consumed in the context of the stream they're in).

The APIs in Rebus are designed to be good at working with queue-based messaging, so when your message handler is invoked, there's no built-in way to know if the message is a part of a stream or to figure out the context. In fact, if processing your message takes just a tiny bit of time (or especially if it happens to await something), Rebus will most likely be processing its neighboring message concurrently. This makes the order of processing non-deterministic, which can be a great scaling trick if your messages can be handled in parallel (which they should) - but if you were working with a stream of messages, you could never have parallelism greater than the number of partitions.

Queues tend to be quick to connect to - log-based brokers tend to have much more protocol associated with producing/consuming messages, because it might need to distribute partitions within topic between a number of consumers withing a consumer group.

I know this wasn't a very well-structured reply 😓 but hopefully you can get an impression why there's a pretty big impedance mismatch between the queue-based and the log-based messaging worlds.

## vs MassTransit

- https://code-maze.com/rebus-dotnet/
- Rebus aims to be more lightweight and easier to configure than MassTransit. It also supports some queuing systems that MassTransit does not, such as Azure Storage Queues and MSMQ, and even relational databases such as SQL Server, PostgreSQL, and MySQL.