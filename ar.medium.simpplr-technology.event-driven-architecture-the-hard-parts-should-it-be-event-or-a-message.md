---
id: pwgwswze16zk9socyr19l9w
title: Event Driven Architecture the Hard Parts Should It Be Event or a Message
desc: ''
updated: 1711402675255
created: 1711402675255
---

- url: https://medium.com/simpplr-technology/event-driven-architecture-the-hard-parts-should-it-be-event-or-a-message-95e2b1815718

## Summary

- If two services have to be communicated different data payload, then messages are the way to go.
- Another situation where you want to use Messages is — if you want to control the sequence of execution in a Workflow. For more details on this type of use case, take a look at this blog [Event Driven Architecture, The Hard Parts : Events Vs Messages](https://medium.com/simpplr-technology/event-driven-architecture-the-hard-parts-events-vs-messages-0fcfc7243703?source=post_page-----95e2b1815718--------------------------------)
  - "With Events, because all the consumers react in parallel, controlling the sequence is tough. Messages help to achieve this sequential execution when needed."