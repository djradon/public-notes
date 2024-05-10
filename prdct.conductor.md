---
id: 2rnf786n2ba5fyjttnx2deq
title: Conductor
desc: ''
updated: 1715365869328
created: 1711403157311
---

- dead
- repo: https://github.com/danielgerlag/conductor
- built_on: [[prdct.workflow-core]]
- written_in: c#

![[prdct.infinitic#similar]]

## Description

Conductor is a workflow server built upon Workflow Core that enables you to coordinate multiple services and scripts into workflows so that you can rapidly create complex workflow applications. Workflows are composed of a series of steps, with an internal data object shared between them to pass information around. Conductor automatically runs and tracks each step, and retries when there are errors.

Workflows are written in either JSON or YAML and then added to Conductor's internal registry via the definition API. Then you use the workflow API to invoke them with or without custom data.

## Issues

- Conductor uses a JSON-based DSL for workflow definitions ^jf9f3krl2u71