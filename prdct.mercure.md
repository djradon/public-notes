---
id: xp7fzyz8v3hiv6ihabpp1qk
title: Mercure
desc: >-
  open solution for real-time communications designed to be fast, reliable, and
  battery-efficient; modern and convenient replacement for both the Websocket
  API and the higher-level libraries and services relying on it.
updated: 1714667824449
created: 1714236933033
---


- https://mercure.rocks/
- built-on: [[prdct.server-sent-events]]
- written-in: go
- similar: [[prdct.centrifugo]] [[prdct.mercure]] ^ahtfnaeq7g62

## Comparison

![[prdct.websub#websub-vs-mercure]]

### Mercure vs Web Push

The [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API) is a simplex protocol [mainly designed](https://developers.google.com/web/fundamentals/push-notifications/) to send [notifications](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) to devices currently not connected to the application. In most implementations, the size of the payload to dispatch is very limited, and the messages are sent through the proprietary APIs and servers of the browsers' and operating systems' vendors.

On the other hand, Mercure is a duplex protocol designed to send live updates to devices currently connected to the web or mobile app. The payload is not limited, and the message goes directly from your servers to the clients.

In summary, use the Push API to send notifications to offline users (that will be available in Chrome, Android and iOS's notification centers), and use Mercure to receive and publish live updates when the user is using the app

### Mercure vs Centrifugo

- Centrifugo supports more complex and diverse communication protocols beyond SSE, including WebSocket, which is more suitable for environments where high throughput and lower latency are required.
- Centrifugo offers private and public channels, presence channels, and authentication features.
- Scalability: Centrifugo is designed to handle large numbers of concurrent clients, making it suitable for more intensive real-time applications.
- Mercure has that built-in integration with [[prdct.api-platform]]