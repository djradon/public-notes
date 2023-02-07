---
id: xldrjvg4ydm2izgznn4dlz1
title: Projections and Read Models in Event Driven Architecture
desc: ''
updated: 1675527647103
created: 1675527177661
---

- "If you’re storing events and read models in the same relational database (like e.g. [[prdct.marten]] in Postgres), then you can wrap all in a transaction."
- "You could also store events’ ids and ensure their uniqueness. This could be done as part of middleware around your event handler that tries to store the event id and stops processing if it was already handled. It may be part of your inbox pattern deduplication or stored in a dedicated table together with business results wrapped in the database transaction."