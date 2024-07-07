---
id: yqcey40ky3aqprq2rq4uogo
title: Linked Data Target Value Maps
desc: ''
updated: 1720329413981
created: 1720329350797
---

- https://github.com/niklasl/ldtvm
- related: [[prdct.trld]]

## Background

Inferencing is often considered a foundational feature for mechanical semantic interoperability. But it is fairly unheard of outside the semantic web community. Not even in the wider circle of linked data proponents does inference feature as a part of common implementations and services.

Meanwhile the web of data at large continues to grow (with REST APIs and services multiplying, with lots of invention and plenty of code being or waiting to be written for integrations of increasing complexity, with little or no reuse between them). Every need cropping up in and between our organizations which needs to be solved right now thus requires us to write up yet another integration script; batching, caching, indexing and (more or less successfully) keeping track of source updates and deletions.

On the level of terms and shapes of descriptions, metadata experts are mired in perpetuated discussion, more or less related to the crude realities of said integrations. Most crucially, these integrations seldom work for interoperability when multiple perspectives and granularities are taken into consideration. The same patterns are defined and implemented over and over again.

### On OWL Reasoners

There are some things which OWL reasoners are prone to, which makes them cumbersome to integrate in "simpler" applications. A great amount of general intelligence for inferring facts is applied, but not so much is about selection, and handling of granularities and proportions between on the one hand events and qualifications, on the other simpler ("dumbed-down") "shorthand" properties.

- Reasoners produce all inferable triples, instead of triples for a desired target vocabulary or selected combination.
- There is no means to specify which reduction or expansion to use for a desired granularity.
- This general inference process can be unpredictably slow.
