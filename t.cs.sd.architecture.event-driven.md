---
id: ehflhupgftjncjisnmcxyzy
title: Event Driven Architecture
desc: >-
  Event-driven architecture uses events to communicate notable data changes
  between service boundaries
updated: 1708460709601
created: 1669463161648
---

## [[p.hadDefinition]]

- "In an event driven architecture there is no client/server paradigm."

### https://www.confluent.io/kafka-summit-san-francisco-2019/building-event-driven-architectures-with-kafka-and-cloud-events/

- event notification
- event-carried state transfer
- [[t.cs.sd.event-sourcing]]


## Resources 

- https://serverlessland.com/event-driven-architecture/visuals #cool
- https://cloud.google.com/eventarc/docs/event-driven-architectures
- https://medium.com/geekculture/event-sourcing-versus-event-driven-architecture-753aa5a5d0f6
  - [[p.hasHighlight]]  ^973t2iqz9www
    - "the event is used as a data contract to communicate the information" 
    - "The publisher and the consumer must have a common understanding of the message that gets shared."
    - "Should event objects used in the event-sourcing implementation also be directly used for communication? No! When solely depending on events used in the event-sourcing pattern, a direct dependency is created on the application's internal data. By creating a separate contract that represents the exact data change, a direct dependence on the same models is avoided, and internal data models are not leaked."
- https://thenewstack.io/supercharging-event-driven-integrations-using-apache-kafka-and-triggermesh/
  - "The difference between a message and an event can be confusing at first. An event is a notification that a state has changed. A message, however, contains additional information that represents more than just a notification. There is additional data associated with a message. Eventing is like a phone call, but it doesn’t tell you who is on the line or what their message is. A message provides the details of the call — e.g. who called and a transcription of what was discussed."
- https://danieltammadge.com/2021/11/message-brokers-vs-event-brokers/
  - "Often people don’t separate brokers, but in the book Building Event-Driven Microservices, the author div
  - "I have seen a Kafka being used to send time-sensitive events that needed to be consumed by all running subscribers when a non-log based broker should have been used, such as RabbitMQ, AWS SQS or AWS SNS or even REDIS."
- https://danieltammadge.com/2022/07/why-not-having-a-schema-registry-can-be-a-fatal-mistake-in-event-driven-architecture/
- https://apisix.apache.org/blog/2022/09/23/build-event-driven-api/
- https://memphis.dev/blog/why-event-first-programming-changes-everything/ lists benefits of EDA, and has a section on "When should you use event-driven architecture?"
- https://azure.microsoft.com/en-us/blog/events-data-points-and-messages-choosing-the-right-azure-messaging-service-for-your-data/
  - "Events largely fall into two big categories: They either hold information about specific actions that have been carried out by the publishing application, or they carry informational data points as elements of a continuously published stream."
- https://serverlessland.com/event-driven-architecture/visuals/document-event-driven-architectures
  - [[c.mention]] [[prdct.event-catalog]]
- https://www.architecture-weekly.com/p/architecture-weekly-152-6th-november
  - https://waswani.medium.com/event-driven-architecture-the-hard-parts-events-vs-messages-0fcfc7243703
    - "So there is a concern of sequence in which things need to be executed to meet the business requirement. And also, the producer service must know the target services which need to perform the required action which goes against the principle of Event Driven Architecture. With Events, because all the consumers react in parallel, controlling the sequence is tough. Messages help to achieve this sequential execution when needed."


### [[p.hasLearningResource]]

- [[ar.medium.edge-coders.understanding-node-js-event-driven-architecture]]