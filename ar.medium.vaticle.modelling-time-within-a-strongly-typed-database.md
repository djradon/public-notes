---
id: x2tvx8dxd0gwfgkoweegl5t
title: Modelling Time within a Strongly Typed Database
desc: ''
updated: 1700517762224
created: 1697478474599
---

- url: https://medium.com/vaticle/modelling-time-within-a-strongly-typed-database-55ba91ecad62
- [[c.mention]] [[ar.a-brief-ontology-of-time]]

## Issues

- What is the point of intIndex?

## Highlights

- "I personally use lists a lot, as well as dicts, for storage in TypeQL, and there are two circumstances:

    I insert an entire list at once, for example, a session in a log with events, and in this case, I use a dummy “stop” value at the end of each list, so it is easy to get.
    Insert items in a list incrementally, as shown above; in this case, I would match out the index of the current record, add 1 to it (in the client) and insert it in the new list item."

## Text



