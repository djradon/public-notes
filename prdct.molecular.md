---
id: ofgmsyl1k9u3fwqhmaf7kp0
title: Molecular
desc: ''
updated: 1698262670465
created: 1674360309430
---

[[c.software.microservice-frameworks]]
[[p.writtenIn]] #javascript

#url https://moleculer.services/
#repo https://github.com/moleculerjs/moleculer

## [[p.hasFeature]]

-   Promise-based solution (async/await compatible)
-   request-reply concept
-   support event driven architecture with balancing
-   built-in service registry & dynamic service discovery
-   load balanced requests & events (round-robin, random, cpu-usage, latency, sharding)
-   many fault tolerance features (Circuit Breaker, Bulkhead, Retry, Timeout, Fallback)
-   plugin/middleware system
-   support versioned services
-   support [Stream](https://nodejs.org/dist/latest-v10.x/docs/api/stream.html)s
-   service mixins
-   built-in caching solution (Memory, MemoryLRU, Redis)
-   pluggable loggers (Console, File, Pino, Bunyan, Winston, Debug, Datadog, Log4js)
-   pluggable transporters (TCP, NATS, MQTT, Redis, NATS Streaming, Kafka, AMQP 0.9, AMQP 1.0)
-   pluggable serializers (JSON, Avro, MsgPack, Protocol Buffer, Thrift)
-   pluggable parameter validator
-   multiple services on a node/server
-   master-less architecture, all nodes are equal
-   parameter validation with [fastest-validator](https://github.com/icebob/fastest-validator)
-   built-in metrics feature with reporters (Console, CSV, Datadog, Event, Prometheus, StatsD)
-   built-in tracing feature with exporters (Console, Datadog, Event, Jaeger, Zipkin)
-   official [API gateway](https://github.com/moleculerjs/moleculer-web), [Database access](https://github.com/moleculerjs/moleculer-db) and many other modules…


## Resources

- https://techblog.geekyants.com/migrating-your-molecular-project-to-ts