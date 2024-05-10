---
id: a8en7isyzik5007m4p3qkn3
title: Inngest
desc: 'SaaS, scalable, low-latency, event-driven durable execution platform. Supports functions deployed to serverless, servers, or the edge. '
updated: 1715367620397
created: 1715367309138
---

- https://www.inngest.com/
- [[c.Software.Workflow]] 
- https://github.com/inngest/inngest
- written-in: go, typescript

## Pricing

- Team: $50/mo for 100k steps, 100 concurrent functions

## Features

- Build simple linear workflows or complex DAG-based workflows with parallelism and fan-in out of the box. Leverage our step primitives for human-in-the-loop or paused functions which automatically resume based off of conditions being met.

## Description

### What is Inngest?

So events are great. They let you know what's happening. They provide audit trails when things happen. But event-driven systems can be difficult to build. And they're very difficult to audit and debug. Don't get us wrong: if you want to wrangle with Terraform, maybe set up Kafka (I have a soft spot for NATS), build your publishers, subscribers, service discovery, throttling, retries, backoff, and other stuff, it can be done. But it's not exactly "move fast", even if it is very much "break things". You also don't get webhook handling, integrating with external services, change management, or non-technical insight here for free either.

Well, this is where we step in. Inngest provides you with a serverless event-driven platform and DAG-based serverless functions out of the box. Send us events - any and all of them from your own systems. Connect webhooks up to external systems. And then build out serverless functions that run in real-time whenever events are received. That's the short version.