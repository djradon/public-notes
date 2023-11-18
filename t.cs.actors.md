---
id: s1b2hshk9rfo7xvnozu5s03
title: Actors
desc: ''
updated: 1700254867315
created: 1670267347423
---

- [[prdct.orleans]] [[p.invented]] [[t.cs.actors.virtual]]

## Implementations

- [[prdct.comedy]] #javascript
- [[prdct.orleans]] #c-sharp 
- [[prdct.akka]]
- [[prdct.pykka]]
- [[prdct.akka-net]]
- [[prdct.ptolemy]]
- [[prdct.dapr]] #c-sharp
- [[prdct.proto-actor]]
- [[prdct.tarant]]  

## Features

- "Actor model services are stateless and reactive"
  - https://medium.com/nerd-for-tech/the-power-of-message-orchestration-b28f18da603a
    - "Actor instances pass messages to other actor instances when they need them to do something."
    - "Actor instances publish events when they need to tell interested subscribers about something."
## Ideas

- Primary actors initiate a use case and hence are somewhat independent. Secondary actors, on the other hand, are used by the system but they do not interact with the system on their own.
  - "The distinction between ‘’primary ‘’and’’ secondary ‘’lies in who triggers or is in charge of the conversation."

## Resources

- [43 years of actors: a taxonomy of actor models and their key properties](https://dl.acm.org/doi/abs/10.1145/3001886.3001890)
- https://github.com/GetTech-io/awesome-actor
- https://forums.ni.com/t5/Actor-Framework-Documents/Justifying-The-Actor-Framework/ta-p/4207018