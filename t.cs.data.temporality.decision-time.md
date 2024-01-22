---
id: QXEaahMfmhhuIehSOukZ6
title: Decision Time
desc: 'an alternative to the transaction time period for recording the time at which a database entry may be accepted as correct. This enables queries that show the officially recognized facts at a given time, even if there was a delay in committing those facts to the database.'
updated: 1705948898267
created: 1638110598531
---

- for tri-temporal tables, the decision date will never be after the transaction date, while the valid date might still be arbitrary.

## References

- https://dba.stackexchange.com/questions/116497/interpreting-decision-time-dt-in-temporal-databases
- https://en.wikipedia.org/wiki/Temporal_database
- https://www.dolthub.com/blog/2023-08-07-temporal-database/ has a tri-temporal example