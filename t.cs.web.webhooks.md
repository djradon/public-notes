---
id: p4zttv41gjxzmi8cxiqm714
title: Webhooks
desc: ''
updated: 1715623591709
created: 1696537036565
---


## Comparisons

### Webhooks vs Event Consumption

- Webhooks deliver or push events to your clients’ services, requiring them to handle the resulting back pressure. Using a scalable message broker to support consumption can alleviate this burden for your clients. How? By allowing clients to pull events based on their availability.
- Standard webhook systems generally lack event persistence for future audits and replays, a capability inherently provided by persisted message brokers.

## References

- https://dev.to/memphis_dev/comparing-webhooks-and-event-consumption-a-comparative-analysis-37a3