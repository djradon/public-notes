---
id: i06isne3qaroisurls34jso
title: Wolverine
desc: Next Generation .NET Mediator and Message Bus
updated: 1708903571781
created: 1687933176283
---

- [[c.software.message-bus]]
- url: https://wolverine.netlify.app/
- similar_to: [[prdct.masstransit]]
- requires: [[prdct.lamar]] [[prdct.oakton]]
- [[p.workedWith]] [[prdct.marten]]
- [[p.supports]] [[prdct.rabbitimq]]

## Description

- Wolverine is a framework built around the idea of message processing where “messages” could be coming from inline invocation like MediatR or local in process queues or external message brokers through asynchronous messaging ala the much older MassTransit or NServiceBus frameworks.
- Wolverine was largely rescued off the scrap heap and completely rebooted specifically to work in conjunction with Marten as a full blow event driven architecture stack.

## Features

- the message handlers are found by default through naming conventions. But if you hate that, no worries, there are options to use much more explicit approaches.
  - Wolverine happily lets you eschew any of the conventional magic and write explicit code where you would be completely in charge of all the EF Core usage. The importance of being able to immediately bypass any conventions and drop into explicit code as needed was an important takeaway from my earlier FubuMVC failure.

## Issues

- Some folks complain that Wolverine forces you to use Lamar as the DI container for your application, but doing so enabled Wolverine to do the codegen the way that it is.
  - "the fasted DI container is “no DI container”"

## Resources

- https://www.dotnetrocks.com/details/1823

## References

- https://jeremydmiller.com/2024/02/15/answering-some-concerns-about-wolverine/
  - 