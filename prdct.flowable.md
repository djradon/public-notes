---
id: bbyhugutzbcvgfxm1x4x9yx
title: Flowable
desc: >-
  A compact and highly efficient workflow and Business Process Management (BPM)
  platform for developers, system admins and business users. 
updated: 1749313991068
created: 1707698384894
---

- repo: https://github.com/flowable/flowable-engine
- [[c.software.Workflow]]
- written_in: java

## Features

- fully supports the [[prdct.bpmn]], [[prdct.cmmn-case-management-model-and-notation]], and [[prdct.dmn]] open standards.
- data dictionary for type definitions, see https://www.flowable.com/blog/engineering/data-structure-with-data-dictionary
- default tenant backstops regular tenants

## Interesting

- There is no simple way in Flowable to list tasks that have not occurred yet. Tasks are not created until execution gets to them and the engine makes no assumption about what tasks are upcoming or even what the next task is until the last task is complete. Due things to gateways, conditional sequence flows, multi-instance tasks, and workflows that iterate multiple times by looping back on themselves, knowing what tasks are coming up is very difficult, if not impossible without limiting processes or making assumptions... For you, your best alternative is to retrieve and parse the model, find the currently active task and follow the sequence flows out of it.