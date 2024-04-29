---
id: rya3n0upusggufhec8i7rl1
title: REST
desc: representational state transfer
updated: 1714421292564
created: 1683224934976
---

- related: [[t.cs.web.hateoas]]

## Issues

- REST API endpoints are fixed. Each endpoint would give you a pre-determined amount of data, irrespective of how much data the client needs. Squeezing efficiency in such a system leads developers to generate an ever-increasing number of endpoints, each returning a contained set of results. The client would then call them in sequence to generate a view for the end-user.

## References

- https://dgraph.io/blog/post/building-native-graphql-database-dgraph/