---
id: xamtfy8jv5x3uz59ybdffhe
title: iWF
desc: '“workflow as code” execution engine from Indeed, iWF is like an interpreter on Cadence/Temporal'
updated: 1715366086783
created: 1705955640379
---

- [[c.Software.Workflow]]
- repo: https://github.com/indeedeng/iwf
- sdk-support: java, go, and python
- messaging-support: [[prdct.nats]]

## Features

- Workflow As Code

## vs Cadence/Temporal

- The biggest argument of [[prdct.cadence]]/[[prdct.temporal]] over iWF is the “normal looking” of workflow code . Cadence/Temporal let user define a workflow as a single function/method while iWF require to split into different pieces (workflow states).

## Cons

- no c#

## Resources

- https://medium.com/@qlong/iwf-vs-other-general-purposed-workflow-engines-f8f3e3d8993d
- https://medium.com/@qlong/saga-pattern-deep-dive-with-indeed-workflow-engine-b7e82c59e51f
- https://community.temporal.io/t/a-letter-to-cadence-temporal-community/6809
- https://www.reddit.com/r/golang/comments/15iy0su/workflow_as_code_microservice_orchestration/
  - "I used to self host Cadence/Temporal but not doing it anymore. I’m using Temporal cloud behind IWF. Their cloud service is amazing and price is very good for me. I would recommend it if you want to save the headache of maintaining a Temporal or cadence cluster. If you have to host Cadence or Temporal, I would recommend using managed Cassandra from other companies like InstaClustr or DataStax. Because Cassandra is not easy to operate in my experience. If you are running for a smaller load and don’t want to use managed Cassandra , then consider using MySQL or PostgreSQL which are easier to operate"

## References

- https://github.com/indeedeng/iwf-java-sdk
