---
id: fduihffkcncqv40thx8vasf
title: Snowflake
desc: ''
updated: 1698252759318
created: 1697826905320
---

- [[p.mentionedOn]] https://interviewnoodle.com/how-discord-stores-billions-of-messages-big-surprises-in-system-design-e48fa07a2665 d

## Features

- tens of thousands of ids per second in a highly available manner. This naturally led us to choose an uncoordinated approach.

These ids need to be roughly sortable, meaning that if tweets A and B are posted around the same time, they should have ids in close proximity to one another since this is how we and most Twitter clients sort tweets.[1]

Additionally, these numbers have to fit into 64 bits.

## Implementations

- https://github.com/AkashRajpurohit/snowflake-id javascript
- 