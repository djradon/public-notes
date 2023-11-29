---
id: 5o0t67dslcj0vyo8z6yrpgh
title: Server Sent Events
desc: ''
updated: 1701280241642
created: 1700866375044
---


## Cons

- maximum 6 per browser + domain,
- unidirectional, but
  - "When subscribing to an information source, you make one descriptive request in order to receive multiple responses. Specifically, when using GraphQL subscriptions or streaming operations (like with @defer and @stream directives), you do exactly this - you send one request and expect multiple responses (events) in return. Having said this, Server-Sent Events seem like a perfect fit!"


## Comparison

### vs [[prdct.websocket]]

- "Built-in support for reconnection"
- You can only have six concurrent open SSE connections per browser at any one time. This can be especially painful when you want to open multiple tabs with SSE connections. See '[Server-Sent Events and browser limits](https://stackoverflow.com/questions/18584525/server-sent-events-and-browser-limits)' for more information and workaround suggestions.

### References

- https://ably.com/blog/websockets-vs-sse
- https://the-guild.dev/blog/graphql-over-sse
  - mentions: [[prdct.graphql-sse]]