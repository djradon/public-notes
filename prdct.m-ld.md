---
id: t7q534y033uby4hmbvq3lm8
title: m-ld
desc: 'information is available where its used—on mobiles, in browsers, in microservices, anywhere—and it stays up-to-date, automatically.'
updated: 1717083933950
created: 1714684120876
---

- https://m-ld.org/
- [[c.software.data-framework.sharing]]
- creator: @george-svarovsky
- implementation:
  - [[prdct.m-ld-js]]

## Features

- **live and shareable**: 
- [[prdct.shacl]] support, see https://js.m-ld.org/classes/shapeconstrained.html

### Hosted persistence via the Gateway 

- For hosted persistence, we offer the m-ld Gateway, a server which (among other functions) operates as another participant in the domain, and thus keeps its own copy of the data, analogous to an IPFS pinning service. This Gateway service may be offered by the application developer for convenience, but it may also be operated by end user themselves if desired, preserving user control. Just as end users can bring their own pods to a Solid app, they can also bring their own Gateways to these collaborative apps.

## Philosophy

### web app data securely stored in reactive, replicated Linked Data sets

- possible for app developers to meet today's and tomorrow's feature expectations without the high costs and limitations of today's distributed data architectures. This foundational design principle combines ideas from the semantic web (machine-readable publishable interlinked data), personal data stores (user control of user data) and local-first software (collaboration without obligatory third parties).

### Coordination

- There are two approaches to concurrency control that don't need a total ordering of changes. One is called Conflict-free Replicated Data Types (CRDTs), and the other Operational Transformation (OT).
- Humans employ myriad strategies for coordination. You withhold thoughts while someone else is talking. You undo and redo thoughts against new information, both before and after expressing them. You notice conflicts that corrupt the information or render it illogical, apply obvious resolutions, and negotiate others. You actively seek consensus, or delegate decisions.

### Message Delivery

Local-first web applications can still benefit from secure durable storage of data on a server. They also rely on a message delivery mechanism, which in practice must be either a deployed service (like a message broker) or a cloud service. While these are cheap to set up, they may become expensive in the long run due to operational costs, provider markup and service over-specification.





## References

- https://rdfjs.dev/m-ld
- https://m-ld.org/news/#live-and-sharable
- [Web Zero, with m-ld](https://docs.google.com/document/d/1DrMr_PI6P81w1spiUDBTkOJGz0bPS2sZIXhCz51p7CE/edit)
- [Sustainable Web Apps, with m-ld](https://docs.google.com/document/d/17YnR6f8Xp69E09sO3BShSP5H6PXx3sDGNTVxNyvl56s/edit)