---
id: gksoywxa18kxwc9g8r7b2v8
title: Data Temporality
desc: ''
updated: 1705968373068
created: 1634620119007
---

## Assertive Time and Effective Time

- suggested names for transaction time and valid time, where decision time is not used
- [ ] why does transaction time need a period?

## Decision Time

![[t.cs.data.temporality.decision-time]]

## Completion Time

- just made this up, it's like due date but doesn't have the "external constraint" sense 
  - [[p.created]] 2021-10-31
- applies to intended activity (tasks), goals
- could sometimes be represented as "ending instant/period of valid time"
- [[idea.defining-done-is-hard]]

## Probabilistic Time

- Triangle Distribution
  - wrong: "The really nice thing about Triangle distributions is the Mean and the Mode are the same"
- 

## [[TimeML|prdct.timeml]]

- functionInDocument ::= 'CREATION_TIME' | 'EXPIRATION_TIME' | 'MODIFICATION_TIME' | 'PUBLICATION_TIME' | 'RELEASE_TIME'| 'RECEPTION_TIME' | 'NONE' 

## Allen's Interval Algebra

- 13 base relations capture 
- 
- Allen's interval algebra can be used for the description of both temporal intervals and spatial configurations. For the latter use, the relations are interpreted as describing the relative position of spatial objects.

## Solutions

- '[of [[prdct.MariaDB]] and [[prdct.Postgres]]], MariaDB supports temporal tables in the core product and sticks to the SQL:2011 standard most closely. I would recommend MariaDB for those interested in temporal tables in existing SQL databases.' [^1]
- [[prdct.sirixdb]] and [[prct.xtdb]]
- [[prdct.TerminusDB]] and [[prdct.Dolt]]

### Resources

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