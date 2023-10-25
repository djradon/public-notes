---
id: 452mkyh3dtruj1g47mh7jrw
title: Event Grid
desc: ''
updated: 1674621720202
created: 1672319985785
---

[[p.instanceOf]] [[t.cs.sd.architecture.event-driven.event-broker]]

- [[p.similarTo]] [[prdct.google-cloud.eventarc]] [[prdct.aws.event-bridge]]
- [[p.supports]] [[prdct.cloudevents]]

#url https://azure.microsoft.com/en-us/products/event-grid/

- [[p.hasLearningResource]] https://learn.microsoft.com/en-us/azure/event-grid/overview
- [[p.supports]] on-prem deployment via https://learn.microsoft.com/en-us/azure/event-grid/kubernetes/overview

## Comparison 

### [[prdct.azure.event-grid]] vs. [[prdct.azure.event-hubs]] vs. [[prdct.azure.service-bus]]  ^tlbdk95pkgk8

https://learn.microsoft.com/en-us/azure/event-grid/compare-messaging-services

| Service | Purpose | Type | When to use |
| --- | --- | --- | --- |
| Event Grid | Reactive programming | Event distribution (discrete) | React to status changes |
| Event Hubs | Big data pipeline | Event streaming (series) | Telemetry and distributed data streaming |
| Service Bus | High-value enterprise messaging | Message | Order processing and financial transactions |  ^e48anqzd79vy