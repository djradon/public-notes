---
id: GBSREzbRJ0CHXZhKz4NAl
title: Transaction Time
desc: when the data entered the database
updated: 1638192886561
created: 1638163352138
---

- different_from: [[t.cs.data.temporality.valid-time]]

- sometimes transaction time is a single point (instant): creation
- sometimes transaction time is a range (interval): from creation until update (valid-in-database) time
  - valid-in-database end of range is "NOW" until update/deletion occurs
  - if update, the transaction end time should be inferrable (with pretty good accuracy) from creation time for next record
  - if delete, range seems more practical
