---
id: mmytejxznjmj3oakm472yzd
title: Bpmn
desc: ''
updated: 1701199105092
created: 1690521120122
spec: https://www.omg.org/spec/BPMN/2.0/
related:
  - [[prdct.bpmnator]]
---

## Details

- spec is > 500 pages

## Types of Elements

- flow objects
  - ![](/assets/images/2023-11-28-09-22-37.png)
  - events are not specifically technical... just what has happened in the problem domain
  - sub process is a collection of flow objects
  - gateways are commonly about branching, e.g. 
    - exclusive (or) 
    - parallel
- connecting objects
  - ![](/assets/images/2023-11-28-09-25-11.png)
  - sequence
  - message
- pools and swimlanes
  - ![](/assets/images/2023-11-28-09-25-50.png)
  - maybe a pool for each participant/company, and each department is a lane
  - or pool is a domain, lane is a subdomain
  - i.e., establishing responsibilities
    - arrow crossing a lane or a pool, that's a dependency
- artifacts
  - ![](/assets/images/2023-11-28-09-27-54.png)
  - not events, tasks, decision points
  - some kind of persistence

## Example

- 

## References

[[event.2023.bpmn_for_profit_and_fun]]