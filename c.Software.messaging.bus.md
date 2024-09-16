---
id: wctxpmzzsa7eki2rwuxm5k5
title: message bus software
desc: ''
updated: 1714627328140
created: 1697039440928
---

## Criteria

-   **Message queuing model:** How are messages passed between two parties? Is it via a stream or a queue?
-   **Delivery guarantee:** Are messages always delivered at least once, or is this not always the case?
-   **Ordering guarantee:** Are messages delivered in the order they were sent, or are they not?
-   **Throughput and latency:** How many messages can the platform handle, and how fast is the communication? Keep in mind that all these systems can scale to handle increased throughput, and that results will vary based on your system configuration.
-   **Persistence and replayability:** Does the platform store messages and allow for reprocessing if they were missed the first time?

## Resources

- https://gcore.com/learning/nats-rabbitmq-nsq-kafka-comparison/