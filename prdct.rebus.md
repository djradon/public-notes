---
id: e3472xdc0i3144yqep7qwp6
title: Rebus
desc: 'Simple and lean service bus implementation for .NET '
updated: 1707694200886
created: 1707692299145
---

- repo: https://github.com/rebus-org/Rebus
- similar_to: [[prdct.masstransit]]
- supports
  - message bus: 

## Cons

- does not lend itself very well to the streaming nature of event brokers like NATS Streaming and Kafka – I think Topos is a better fit for that.

## vs MassTransit

- https://code-maze.com/rebus-dotnet/
- Rebus aims to be more lightweight and easier to configure than MassTransit. It also supports some queuing systems that MassTransit does not, such as Azure Storage Queues and MSMQ, and even relational databases such as SQL Server, PostgreSQL, and MySQL.