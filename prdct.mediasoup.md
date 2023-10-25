---
id: zhdx5lpw26ayvi8zcfl1j5g
title: Mediasoup
desc: ''
updated: 1698252759276
created: 1696356637338
---

- #url https://mediasoup.org/
- [[p.builtOn]] [[prdct.webrtc]]

## #description

- An SFU (Selective Forwarding Unit) receives audio and video streams from endpoints and relays them to everyone else (endpoints send one and receive many). Each receiver endpoint can select which streams and spatial/temporal layers it receives. Compared to a mixer or MCU (Multipoint Conferencing Unit) this design leads to a better performance, higher throughput and less latency. It's highly scalable and requires much less resources given that it does not transcode or mix media. Since endpoints get the other endpoints' media separately, they can have a personalized layout and choose which streams to render and how to display them.

## Features

- perfect choice for building multi-party video conferencing and real-time streaming apps.
- Instead of creating yet another opinionated server, mediasoup can be used as Node.js module or Rust crate which can be integrated into a larger application.
- comes with mediasoup-client (JavaScript library) and libmediasoupclient (C++ library) for building applications that run in any browser or device by using an unified API. Or just use well known software such as FFmpeg or GStreamer.

## Thoughts

- spatial and temporal layers seems to refer to the size and framerate of the provided video. 