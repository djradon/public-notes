---
id: vm1ue4g4ympj6kc1d7qyshn
title: Inmemory Message Bus in TypeScript
desc: ''
updated: 1713188962527
created: 1713188926791
---

- https://event-driven.io/en/inmemory_message_bus_in_typescript/

## Highlights

### Direct and Indirect Communication

There are two ways of communicating: direct and indirect. For direct communication, we ask another component to perform a specific action and want to know if that happened. For indirect communication, we notify others that something has happened and let them decide what to do. In a nutshell, direct is represented by command, and indirect by event. Read more in What’s the difference between a command and an event?.

Typically, direct communication is assumed to be blocking and indirect non-blocking, but that’s a common practice, not a rule. Both types of communication can be blocking or non-blocking. In the real world, we may ask other people to do something and wait until they finish or assume that they will reply to us when they have done it. For indirect communication, even though we’re not interested in what will happen after we broadcast news, we’d like to know whether all interested parties took action.

