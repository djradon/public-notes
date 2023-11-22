---
id: knr70d98u0tqx338yeii27u
title: Rustconf Talk
desc: ''
updated: 1696891769195
created: 1696707625159
---

- url: https://kyren.github.io/2018/09/14/rustconf-talk.html
- [[c.actor.speaker]] @kyren

## [[c.text.exerpt]]

- [with oo] "It feels like every time a new requirement comes in, you have to take what may have once been sane interfaces and “poke more holes through them”."
- Data hiding has very limited utility for a game outside of just maintaining invariants at the edges of the code, where things are smaller and more contained. A lot, possibly even the vast majority of the interesting behavior in your game ends up spanning many data types, and does not naturally “belong” to any specific entity. Lots of entity types are 80% or 60% similar to others and its hard to re-use code, and the more modules we add inside our entities to help reuse code, the more layers are added.

- Not everybody entirely agrees with what OO is, but I’m including some basic hopefully non-controversial points: ^hkms0rjrw5lz
  -   Single responsibility principle - Objects should have a single logical set of responsibilities, and methods should perform one operation inside that set of responsibilities. 
  -   Encapsulation - You should bind data together with the functions that operate on it, keeping both safe from outside interference and misuse. This allows for refactoring by changing the internal representation of a class without changing its behavior.
  -   Abstraction, or “Liskov Substitution Principle”, or similar - You should be able to substitute one derived class for another, as long as they share the same base and are used through that base class (or interface, or whatever).
  -   Interface segregation, or principle of least coupling, etc - The dependency on one class to another should use the smallest possible interface. 

- there are at least a few good ideas that are sort of related to OO or kind of came out of OO (all of which Rust has and can perform admirably). ^c47v165vrmv6
  -   The dot operator or “postfix functions”. If you’re a haskeller this is “type directed name resolution” as opposed to the normal state of affairs which is “name directed type resolution”. A “powerful” way to avoid having to scope 100 different functions with very short common names, or have C style prefixes for everything. Great for IDEs too!
  -   Interfaces with laws (contracts) - Rust traits! No inheritance in sight, and they’re best when they’re small and come with meaningful rules around them, but if you squint they’re kind of C++ pure virtual classes. They’re _awesome_ in the same way Haskell typeclasses are awesome.
  -   Data hiding - Being able to hide data to maintain invariants is invaluable, making a safe interface to unsafe code would not be possible without it. Very useful in the small, and with “library” code.

