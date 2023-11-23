---
id: 5izi3fbls7d833qc45ozeaq
title: AsyncAPI
desc: ''
updated: 1699199448853
created: 1673569081430
---

- related: [[prdct.asyncapi.modelina]]

## Highlights

- "Like with OpenAPI, an AsyncAPI documents an application from the client perspective."
- "there is no client/server paradigm... AsyncAPI approaches this by describing an application as having two potential roles:
  - If it sends messages to a channel, it's a “Publisher".
  - If it is interested in receiving messages from a channel, it is a “Subscriber"...
  - The exception to the rule is websockets - there is a client/server paradigm rather than a messaging infrastructure - so other applications will connect directly to the server."

## Comparison

## [[c.comparand]] [[prdct.openapi]] 

- https://www.asyncapi.com/blog/openapi-vs-asyncapi-burning-questions
  - ![](/assets/images/2023-09-29-11-33-20.png)
- https://stackoverflow.com/questions/67055564/how-to-document-a-mixture-of-synchronous-and-asynchronous-apis-do-we-use-asynca
- https://bump.sh/blog/asyncapi-vs-openapi
- https://www.asyncapi.com/docs/tutorials/getting-started/coming-from-openapi
  - 

## [[c.comparand]] [[prdct.cloudevents]]

- https://www.asyncapi.com/blog/asyncapi-cloud-events
  - "Unlike CloudEvents —who focuses on the message— AsyncAPI does not impose how your event must look like but, instead, allows you to strictly define its shape."
  - "We can define the event payload but its structure is totally free and user-defined. And that's what makes AsyncAPI so powerful! Since our event payload can be anything, it can also be a CloudEvents event."
- https://atamel.dev/posts/2023/05-23_asyncapi_cloudevents/
  - CloudEvents help to define the format of the events and AsyncAPI helps to define the event-driven APIs.

## Resources

- https://www.asyncapi.com/blog/websocket-part1
- https://nordicapis.com/7-protocols-good-for-documenting-with-asyncapi/
  - includes [[prdct.nats]]
- https://blog.postman.com/asyncapi-joins-forces-with-postman-future-of-apis/
- https://www.asyncapi.com/blog/designing_your_apis_with_asyncapi_part_1
- [](https://github.com/jonaslagoni/asyncapi-miniseries/blob/master/docs/Part%201%20-%20Designing%20the%20API's.md)
  - "I always start with the basics and define all the different channels for which the game server should produce events over."
  - mentions: Nic Townsend's post about [Demystifying the Semantics of Publish and Subscribe](https://www.asyncapi.com/blog/publish-subscribe-semantics).
- https://icepanel.medium.com/asyncapi-for-event-driven-architectures-b08d6ee952fc
- https://www.asyncapi.com/blog/publish-subscribe-semantics
  - "When reading an AsyncAPI document:

    publish means publish an event to the channel and this application will receive it
    subscribe means subscribe to this channel to receive events published by this application"

### c#

- [[prdct.asyncapi.template.c-sharp]]