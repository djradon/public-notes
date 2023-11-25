---
id: s1b2hshk9rfo7xvnozu5s03
title: Actors
desc: ''
updated: 1700887914831
created: 1670267347423
---

- [[prdct.orleans]] [[p.invented]] [[t.cs.actors.virtual]]

## Implementations

- [[prdct.comedy]] javascript
- [[prdct.orleans]] c# 
- [[prdct.akka]]
- [[prdct.pykka]]
- [[prdct.akka-net]]
- [[prdct.ptolemy]]
- [[prdct.dapr]] c#
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
- https://clojure.org/about/state
  - "the actor model was designed to address the problems of distributed programs. And the problems of distributed programs are much harder - there are multiple worlds (address spaces), direct observation is not possible, interaction occurs over possibly unreliable channels, etc... I chose not to use the actor model for same-process state management in Clojure for several reasons:

    -   It is a much more complex programming model, requiring 2-message conversations for the simplest data reads, and forcing the use of blocking message receives, which introduce the potential for deadlock. Programming for the failure modes of distribution means utilizing timeouts etc. It causes a bifurcation of the program protocols, some of which are represented by functions and others by the values of messages.
        
    -   It doesn’t let you fully leverage the efficiencies of being in the same process. It is quite possible to efficiently directly share a large immutable data structure between threads, but the actor model forces intervening conversations and, potentially, copying. Reads and writes get serialized and block each other, etc.
        
    -   It reduces your flexibility in modeling - this is a world in which everyone sits in a windowless room and communicates only by mail. Programs are decomposed as piles of blocking switch statements. You can only handle messages you anticipated receiving. Coordinating activities involving multiple actors is very difficult. You can’t observe anything without its cooperation/coordination - making ad-hoc reporting or analysis impossible, instead forcing every actor to participate in each protocol."

