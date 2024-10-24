---
id: 1daiwc3t08zkfn67ojf8c6h
title: Unique Identifiers
desc: ''
updated: 1729802524891
created: 1715752682898
---

## Thoughts

- IRIs are identifiers, 
- [with k-sortable IDs,] You may be allowing your storage needs to escape abstraction layers. 
- "If you ever make these values end-user visible, you are leaking info that you might not realize... why should Alice be allowed to know, to within a second, when Bob created their account? This could be misused, or dangerous, in some applications. "

## Possible Solutions

[[prdct.ulid]]: 128-bit UUID compatible, with 48 bits timestamp, 80 bits random.

[[prdct.snowflake]]: 64-bit, with 41 bits timestamp, 10 bits machine ID, 12 bits per-machine sequence. This may be the oldest, but one of the most relevant as it was invented by Twitter, and both Discord and Instagram are using variations of it.

[[prdct.uuid.v6]]: 128-bit UUID, with 64 bits timestamp (minus 4 bits UUID version embedded in it), 2 bits UUID variant, 14 bits “clock sequence”, and 48 bits random. Has a non-expired IETF draft.

[[prdct.ksuid]] (K-Sortable Unique IDentifier): 160-bit, with 32 bits timestamp and 128 bits random. Created by Segment and probably mostly in use internally to them as well.

Stripe IDs: Like ch_1Iyqf42eZvKYlo2C4MIyA80e, are a combination of timestamp and random bits and base62 (-ish) encoded, although I don’t remember the proportions and didn’t spend the time reverse engineering them.

Flake: 128-bit, with 64 bits timestamp, 48 bits machine ID, and 16 bits sequence. Created by Boundary (which is under new management) in Erlang, and best considered deprecated.

[[prdct.nanoid]]  A ~~tiny~~ (124 bytes), secure, URL-friendly, unique string ID generator for JavaScript 


## References

- https://brandur.org/fragments/k-sorted-ids
- https://www.reddit.com/r/golang/comments/10bg0rn/which_uuid_package_do_you_use_and_why/
- https://deepam-kapur.medium.com/ulid-and-snowflake-id-the-cool-coders-alternative-to-boring-uuids-1e772064f275