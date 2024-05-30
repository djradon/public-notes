---
id: colifmdgrpheolby8rpaunn
title: json-rql
desc: 'JSON Resource Query Language, for simple, consistent query APIs'
updated: 1717088042078
created: 1714685111523
---

- https://json-rql.org/
- based-on: [[prdct.json-ld]]
- related: [[prdct.m-ld]]

## Description

- a convention for expressing queries against structured resources, using JSON. It helps resolve the tensions between expressibility and simplicity, and between agility and future-proofing, in API design. It is based on JSON-LD.
- It's [[prdct.json]]: straightforward to construct in code, manipulate and serialize, and also to constrain. Use standard JSON tooling such as JSON schema to limit your API to the queries that your back-end has been designed and tested for.
- It's [[prdct.sparql]]: in context, all queries can be translated to the W3C standard language for directed, labeled graph data. This means that your API can be extended to cover future query requirements, without breaking changes.

