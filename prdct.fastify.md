---
id: ldecp48tsbebdt5joi0mmkd
title: Fastify
desc: 'web framework focused on developer experience and plugin architecture, inspired by Hapi and Express'
updated: 1672414469679
created: 1672412440061
---

#repository https://github.com/fastify/fastify

- [[p.supportedBy]] [[prdct.nestjs]]

## [[p.hasFeature]]

-   **Highly performant:** as far as we know, Fastify is one of the fastest web frameworks in town, depending on the code complexity we can serve up to 76+ thousand requests per second.
-   **Extendible:** Fastify is fully extensible via its hooks, plugins and decorators.
-   **Schema based:** even if it is not mandatory we recommend to use [JSON Schema](https://json-schema.org/) to validate your routes and serialize your outputs, internally Fastify compiles the schema in a highly performant function.
-   **Logging:** logs are extremely important but are costly; we chose the best logger to almost remove this cost, [Pino](https://github.com/pinojs/pino)!
-   **Developer friendly:** the framework is built to be very expressive and help the developer in their daily use, without sacrificing performance and security.