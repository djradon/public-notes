---
id: k9okwkmd5b2xr6qwefn6f5l
title: Janus WebRTC
desc: ''
updated: 1714484766218
created: 1649976868078
---

- repo: https://github.com/meetecho/janus-gateway
- [[p.hasSite]] https://janus.conf.meetecho.com/
- [[p.differentFrom]] `prdct.janusgraph`
- scripting-language-support: [[prdct.lua]] [[prdct.duktape]]/javascript
- related: 

## Topics

## Data Channels

- The TextRoom plugin, as the very original name suggests, basically implements text-based messaging over data channels. More specifically, it allows you to create and/or join multiple “chatrooms” on the same data channel, and exchange public and/or private messages with the other participants. This all happens using a custom JSON-based protocol with a defined syntax for requests, responses/errors and events. It’s important to point out that this protocol is NOT the same as Janus API: it is a protocol that only makes sense to the plugin itself.
  - Another interesting property this plugin has is its “forward externally” functionality. Very simply, when properly configured, this plugin can make sure that any message addressed to a specific room is forwarded to an external web server via HTTP. This can be useful for different use cases: e.g., for archiving purposes, where an external component tracks all exchanged messages; or as a simple and effective way of relaying commands from a browser to a non-WebRTC component (e.g., for IoT purposes). At the time of writing, though, there’s no way to go the opposite way, that is injecting external messages into a data channel only conversation.

### Temporal Layer

allows a video stream to be encoded at multiple resolutions and quality levels. The "temporal layer" in this context specifically deals with the temporal resolution of the video stream, meaning it relates to different frame rates included within the same video stream.


## Demos

### Data Layer

- [distributed remote control for a Janus-based SocialTV application](https://youtu.be/QkjIIh0cqcM?t=211); in another I used them in a custom plugin to implement a [web-based terminal shell](https://youtu.be/d0zHiLkHDyY?t=2780); in yet another I chose them as a way to [send ARI commands to Asterisk via the Lua plugin](https://youtu.be/fOUiVBaZgnQ?t=2682).