---
id: 6qiwgmwcble6kyeq22l2rfh
title: Events Vs Messages
desc: 'a message is sent to a pre-determined location, whereas an event is broadcast to any potential listeners'
updated: 1678139656769
created: 1672332370168
---



A Message is some data sent to a specific address. In Message Driven systems, each component has a unique address other components can send messages to. Each of these components, or recipients, awaits messages and reacts to them.

An Event is some data emitted from a component for anyone listening to consume.

## [[p.provokedThoughts]]

- it's a slim difference
  - permissioned event queues are similar to broadcast messages
  - you could imagine 

## [[p.hasRelatedResource]]

- https://azure.microsoft.com/en-us/blog/events-data-points-and-messages-choosing-the-right-azure-messaging-service-for-your-data/
- https://thenewstack.io/supercharging-event-driven-integrations-using-apache-kafka-and-triggermesh/