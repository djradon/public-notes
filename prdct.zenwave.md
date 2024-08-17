---
id: e7cwry6srena3je114i12b8
title: Zenwave
desc: 'toolkit for Domain Driven Design (DDD) and API-First that can generate code from a mix of different models including:

    JHipster Domain Language (JDL)
    AsyncAPI
    OpenAPI
'
updated: 1723910164504
created: 1706228582009
---

- repo: https://github.com/ZenWave360/zenwave-sdk
- written-in: java
- supports: [[t.cs.sd.domain-driven-design]], [[t.cs.sd.architecture.event-driven]], [[prdct.jhipster.jdl]], [[prdct.karate]]


## Description

- ZenWave Domain Language started as an extended subset of JHipster Domain Language (JDL) that let you describe your entities and relationships.


## Workflow

-   Start by **Modeling your Domain** using the ZDL Domain Language including: entities, relationships, service commands and domain events.
-   Generate a **draft OpenAPI definition from the ZDL model**. Edit collaboratively this OpenAPI document and then generate some more functional code and tests from that definition.
-   Generate a **draft AsyncAPI definition** for consuming async request commands and publishing domain events. Now use zenwave maven plugin to generate strongly typed business interfaces implementing some Enterprise Integration Patterns like: transactional outbox, business dead letter queue...
-   Generate a **complete Backend Application** from your Domain Definition Model.
-   Connect (by hand) your Backend Application to other systems using the generated OpenAPI and AsyncAPI definitions.
-   Generate **E2E, Integration tests and Consumer Contracts** for the public APIs you just produced.