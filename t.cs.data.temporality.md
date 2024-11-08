---
id: gksoywxa18kxwc9g8r7b2v8
title: Data Temporality
desc: ''
updated: 1731024725268
created: 1634620119007
---


## Assertive Time and Effective Time

- suggested names for transaction time and valid time, where decision time is not used
- [x] why does transaction time need a period?
  - if you have a history of transactions, the "current" state has no tx-end. old states have a timestamp of when they were superseded. Seems like you could impute an old state's tx-end tho, but I bet for querying, having the tx-end stored is nice.
  - t.2024.07.12.14 in open-world assumption, or in cases of gaps where a fact gets (soft-)deleted and then re-created
  - for clarity, perhaps "record-commissioned-at" and "record-decomissioned-at"

## Decision Time

![[t.cs.data.temporality.decision-time]]
- t.2024.07.12.14 probably just "an application time"

## Completion Time

- just made this up, it's like due date but doesn't have the "external constraint" sense 
  - [[p.created]] 2021-10-31
- applies to intended activity (tasks), goals
- could sometimes be represented as "ending instant/period of valid time"
- [[idea.defining-done-is-hard]]
- t.2024.07.12.14 probably just another application time

## Probabilistic Time

- Triangle Distribution
  - wrong: "The really nice thing about Triangle distributions is the Mean and the Mode are the same"
- 

## [[TimeML|prdct.timeml]]

- functionInDocument ::= 'CREATION_TIME' | 'EXPIRATION_TIME' | 'MODIFICATION_TIME' | 'PUBLICATION_TIME' | 'RELEASE_TIME'| 'RECEPTION_TIME' | 'NONE' 

## Allen's Interval Algebra

- see [[t.cs.time.allens-interval-algebra]]

## Solutions

- '[of [[prdct.MariaDB]] and [[prdct.Postgres]]], MariaDB supports temporal tables in the core product and sticks to the SQL:2011 standard most closely. I would recommend MariaDB for those interested in temporal tables in existing SQL databases.' [^1]
- [[prdct.sirixdb]] and [[prdct.xtdb]]
- [[prdct.TerminusDB]] and [[prdct.Dolt]]
- [[prdct.strabon]] and [[prdct.allegrograph]]

## Resources

- [[ar.psu.decision-time-in-temporal-databases]]
- [[ar.au.semantics-of-temporal-models-with-multiple-temporal-dimensions]]
- https://aclanthology.org/2021.naacl-main.67.pdf
- [DESIGN AND IMPLEMENTATION OF HLA TIME MANAGEMENT IN THE RTI VERSION F.0](https://www.informs-sim.org/wsc97papers/0373.PDF)
- https://robinpokorny.medium.com/why-developers-should-stop-using-iso-8601-for-date-time-e6ee5fc8ad87
- https://medium.com/towards-nesy/temporal-logic-model-checking-cf05fc917688
- https://herdingcats.typepad.com/my_weblog/2006/02/deterministic_v.html
  - has a comment preferring PERT (Project Evaluation and Review Technique) distribution: (Min+4*Mode+Max)/6
- https://en.wikipedia.org/wiki/Allen%27s_interval_algebra
- [[ar.bitemporal-data-model-making-it-happened-in-postgres]]
- [^1]: https://www.dolthub.com/blog/2023-08-07-temporal-database/
- https://blog.podsnap.com/bitemp.html
- https://realfiction.net/posts/2d-or-bitemporal-historization-a-primer/
- [[book.bitemporal-data-theory-and-practice]]
- [[ar.enabling-retroactive-computing-through-event-sourcing]]
- [ ] [[ar.fuzzy-spatiotemporal-data-modeling-and-operations-in-rdf]]
- [ ] [[ar.towards-semantic-identification-of-temporal-data-in-rdf]]