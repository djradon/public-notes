---
id: 4gu7lt06d8ngf81sssaynp3
title: V8
desc: ''
updated: 1715661276225
created: 1715661153177
---

## Comparisons

### UUIDv7 vs UUIDv8

UUID v8 is a open format, where just the version and variant bits are fixed. This custom implementation is similar to UUID v7 with two major changes:

    The time granularity has been increased from 1 millisecond to 20 microseconds. With UUID v7 you can create a sortable UUID every ~250 ns, with this implementation of UUID v8 sorting will work up to a creation rate of ~5 ns. The UUID v7 will overflow in ~8900 years, this UUID v8 implementation will overflow in ~120 years.

    The CSPRNG random number generation has been replaced for the xoshiro256++ algorithm, which is not cryptographically secure. Therefore, this implementation should NOT be used for generation of cryptographic keys. UUID v4 is still the best option for cryptographic key generation due to its 122 pseudo-random bits. However, for creating unique identifiers where security is not important, such as database identifiers, this scheme is more performant, sortable, and a higher bit variety than UUID v7 due to the incread time granularity as mentioned above.


## References

- https://www.ietf.org/archive/id/draft-peabody-dispatch-new-uuid-format-01.html#name-uuidv8-node-usage