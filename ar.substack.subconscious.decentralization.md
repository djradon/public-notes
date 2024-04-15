---
id: 5efwjmjvaaasfsv4sg6sr67
title: Decentralization
desc: ''
updated: 1713141507205
created: 1712989752141
---

- https://subconscious.substack.com/p/decentralizability
- 

## Highlights

### What is the minimum set of mechanisms we need to make software decentralizable?

Some answers will vary from project-to-project, but I see some common patterns:

- Immutable data
- Universal identifiers
- User-controlled keys

### Things fall out of sync, or rather, they were never in sync to begin with. 

So, we often need mechanisms to resolve conflicting understandings of the world.

Instead of trying to modify a single shared state, just pass messages. Each message is immutable—it doesn’t change after being sent. That means the message can be sent to many different places and these places don’t need to coordinate to find out if the message has changed. It won’t.

How do you represent change? Multiple messages can tell a story about how something changes. This is how Git, CRDTs, [[prdct.nostr]], and [[prdct.noosphere]] model changes.

### Universal Identifiers

At some point you’re going to want to be able to identify some data independent of where it lives.

  - UUID4
  - Content hashes
    - have a 1:1 correspondence with content
    - self-verifying
    - not friendly

- t.2024.04.14.17 why no mention of URIs?


## References

- [[ar.substack.subconscious.the-minimal-definition-of-user-agency]]