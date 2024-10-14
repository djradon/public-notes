---
id: df6lxpcg1811oc1iwsfaoq2
title: Graphology
desc: 'robust & multipurpose Graph object for JavaScript and TypeScript.'
updated: 1728865334931
created: 1656521898305
repo: https://graphology.github.io/
features:
  - nice serialization/deserialization to json

cons:
  - no query language

similar:
  - [[prdct.ngraph]]
  - [[prdct.graphlib]]

related:
  - [[prdct.graphology-gremlin]]
  - [[prdct.cypher-query]]
---

- [[c.software.database.graph.property]]
- [[p.isComponentOf]] [[prdct.sigma-js]]
- resources: 
  - https://archive.fosdem.org/2017/schedule/event/graph_library_javascript/attachments/slides/1803/export/events/attachments/graph_library_javascript/slides/1803/Graphology___FOSDEM_2017.pdf


## Examples

### native filtering

```
// From a filtering function
const sub = subgraph(graph, function (key, attr) {
  return key.startsWith('J') || attr.color === 'red';
});
```

### copying to array (from @chatgpt.3.5), yuck

```
const { Graph } = require('graphology');

const graph = new Graph();

graph.addNode('Alice', { age: 30 });
graph.addNode('Bob', { age: 25 });

const nodesOver25 = Array.from(graph.nodes()).filter(node => graph.getNodeAttribute(node, 'age') > 25);
```