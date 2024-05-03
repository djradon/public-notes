---
id: up5kba2yaqoquzndu9thqzy
title: WebSub
desc: >-
  WebSub provides a common mechanism for communication between publishers of any kind of Web content and their subscribers, based on HTTP webhooks.
updated: 1714771012177
created: 1712555496806
---

- url: https://www.w3.org/TR/websub/

## Similar 
- [[prdct.websub]] [[t.cs.web.webhooks]] [[prdct.linked-data-notifications]]

## Implementations

- [[prdct.websubhub]]

## Issues

- "Hubs push the contents to all the subscribers who have subscribed to the topics and publishers share their content with Hubs, so here publishers and subscribers are completely unknown to each other. Private information shared by publishers may reach hundreds of unknown subscribers."
  - t.2024.05.02.06 but really, isn't that true of all pubsub messaging? 

## Comparison

### WebSub vs Mercure

- WebSub is a server-to-server only protocol, while Mercure is also a server-to-client and client-to-client protocol.

- Mercure has been heavily inspired by WebSub, and we tried to make the protocol as close as possible from the WebSub one.

- Mercure uses Server-Sent Events to dispatch the updates, while WebSub use POST requests. Also, Mercure has an advanced authorization mechanism, and allows to subscribe to several topics with only one connection using URI templates.

## WebSub vs Linked Data Notification

-   **WebSub:**
    
    -   Prioritize simplicity and established usage.
    -   Need immediate distribution of content updates without a focus on detailed structure.
    -   Primarily concerned with human-readable content.
    
-   **LDN:**
    -   Require structured notifications that can be easily integrated with other Semantic Web systems.
    -   Want notifications themselves discoverable and queryable.
    -   Machine interpretability is a strong requirement.

## References

- https://ably.com/topic/websub
- https://ayesh9303.medium.com/learning-websub-part-1-introduction-to-websub-94ee99a09a70
- https://mercure.rocks/docs/spec/faq