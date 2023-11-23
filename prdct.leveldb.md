---
id: bHcvNZBwNgwGxdzjRotMH
title: LevelDB
desc: ''
updated: 1696269809574
created: 1645158420618
---

- repo: https://github.com/google/leveldb
- written-in: #c++


## Cons

-   This is not a SQL database. It does not have a relational data model, it does not support SQL queries, and it has no support for indexes.
-   Only a single process (possibly multi-threaded) can access a particular database at a time.
-   There is no client-server support builtin to the library. An application that needs such support will have to wrap their own server around the library.



