---
id: yxly4t5qf9s98dxujeq2u78
title: Kestra
desc: 'open-source orchestrator designed to bring Infrastructure as Code (IaC) best practices to all workflows — from those orchestrating mission-critical applications, IT operations, business processes, and data pipelines, to simple Zapier-style automations'
updated: 1715379466514
created: 1715359575586
---

- https://kestra.io/
- [[c.Software.Workflow]]
- license: 
  - [[lic.apache.2]] for open-source version
  - enterprise edition has security, governance, and scalability
- written-in: java

![[prdct.infinitic#similar]]

## Features

- Write your business logic in any language. Kestra supports Java-based plugins as well as scripts written in Python, R, Julia, Ruby, Shell, Powershell and Node.js.
- Flow execution based on event triggers including file detection, message queues, completion of certain flows, or results of a SQL query or API call.

### Runners

- JDBC Runner: Ideal for environments preferring traditional databases, this runner supports H2, PostgreSQL, and MySQL for both queueing and repository functions.
- Kafka Runner: For more demanding scalability requirements, this runner employs Kafka for queue and Elasticsearch for repositary, available exclusively in the enterprise edition.

### Plugins

- **Git Plugin**: this plugin allows you to pull code from any Git repository at runtime, making it easier to execute custom scripts in Python, SQL, or other languages. You can set a custom branch name and configure authentication to private repositories.See the example below and [learn more about the Git plugin.](https://kestra.io/plugins/plugin-git)
- **NATS Plugin**: this plugin allows you to trigger flows based on new messages in the [nats.io](https://nats.io/) distributed system. There’s also a task to consume or produce new messages. See the [NATS plugin documentation](https://kestra.io/plugins/plugin-nats) for more details.


## Support

### 