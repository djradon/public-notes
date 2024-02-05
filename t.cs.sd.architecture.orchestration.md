---
id: 08k9bzf078nrt71hp1rxaao
title: Orchestration
desc: still need a component that is aware of the entire workflow
updated: 1705954572460
created: 1680909338629
---

![](/assets/images/2023-10-06-14-20-41.png)
- related: [[t.cs.sd.architecture.choreography]]
  - but they're not opposites; it's kinda a false distinction. if systems determine their behavior based on messages, and the messages are "do this by then", you're getting orchestrated


## Implementations

- [[prdct.workflow-core]]
- [[prdct.prefect]]
- [[prdct.temporal]]

## Resources

- https://dzone.com/articles/orchestration-pattern-managing-distributed-transac
  - "We have designed an appropriate architecture where all services operate within their bounded context. However, we still need a component that is aware of the entire business workflow."
- 