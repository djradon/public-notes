---
id: zg536sp9c87sy4lgv1wqn8n
title: Workflow
desc: ''
updated: 1715366639529
created: 1690382238505
---

## Comparisons

### Orchestration/Workflow Engines vs Rules/Process Engines

- Rules Engine: Choose when you need to centralize complex business logic, codify a large set of rules and decisions, and require clarity around why certain decisions are made.
- Process Engine: Choose when you have structured business processes with well-defined steps and a need for visual process flow representation (BPMN).
- Orchestration Framework: Use when you need to coordinate activities across multiple microservices, manage long-running processes that span multiple systems, or require fault tolerance and scalability in a distributed environment
- Rules/process engines are often used for decision automation and process automation within a single application,
-  orchestration frameworks are more suitable for orchestrating distributed, event-driven workflows involving multiple services or external systems.
- In practice, these two paradigms can be combined, where orchestration frameworks can leverage rules/process engines for decision-making or process automation within individual tasks or steps of a larger orchestration workflow.

## Resources

- https://github.com/meirwah/awesome-workflow-engines
