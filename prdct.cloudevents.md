---
id: 8cs1j4m6abso08lz9kxbef3
title: Cloudevents
desc: 'A specification for describing event data in a common way'
updated: 1674375834074
created: 1672335135527
---

#url https://cloudevents.io/

- [[p.supportedBy]] [[prdct.openfaas]] [[prdct.triggermesh]] [[prdct.kafka]] [[prdct.quarkus]]

## [[p.hadDefinition]]

### https://quarkus.io/blog/kafka-cloud-events/

- Events can be used to implement event sourcing, communicate facts, trigger out-of-band processing, or send notifications. Events become an essential piece of any system.


## [[p.hasRelatedResource]]

- https://developers.redhat.com/blog/2021/03/09/an-introduction-to-javascript-sdk-for-cloudevents
  - "Currently, there are two event formats: Binary, which is the preferred format, and structured. Binary is recommended because it is additive. That is, the binary format only adds some headers to the HTTP request. If there is a middleware that doesn’t understand CloudEvents, it won’t break anything, but if that system is updated to support CloudEvents, it starts working."