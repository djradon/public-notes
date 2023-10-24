---
id: cxy3sruhn88twl144ozfhnx
title: Traits
desc: ''
updated: 1698168477353
created: 1671553437341
---

- [[p.similarTo]] [[t.cs.sd.mixin]]

## [[p.hadDefinition]]

"You don't really care for IS-A -- you really only care for BEHAVES-LIKE-A-(in-this-specific-context), so, if you do test, this behaviour is what you should be testing for."
  - @alex-martelli

"A better, more modern way to implement OOP is using traits."
  - https://itnext.io/straits-9ef2b9a563cd

## [[p.vs]] [[t.cs.sd.mixin]] ^bx54pp894a62

- The main difference between traits and alternative composition techniques such as multiple inheritance and mixins is that upon trait composition, name conflicts (a.k.a. name clashes) should be explicitly resolved by the composer. This is in contrast to mixins and multiple inheritance, which define various kinds of linearization schemes that impose an implicit precedence on the composed entities, with one entity overriding all of the methods of another entity. While such systems often work well in small reuse scenarios, they are not robust: small changes in the ordering of mixins/classes somewhere high up in the inheritance/mixin chain may impact the way name clashes are resolved further down the inheritance/mixin chain. In addition, the linearization imposed by mixins/multiple inheritance precludes a composer to give precedence to both a method m1 from one mixin/class A and a method m2 from another mixin/class B: either all of A's methods take precedence over B, or all of B's methods take precedence over A.
  - https://github.com/traitsjs/traits.js

## [[c.Implementation]]

- #php has traits with properties
  - https://stackoverflow.com/questions/47727003/can-traits-have-properties-methods-with-private-protected-visibility-can-tr
- #javascript has traits with symbol:
  - "Recent versions of JavaScript (i.e. ECMAScript 6) added a new primitive data type, symbol, which can be used to implement traits effectively. A symbol is basically a unique identifier that can be used as a property and that will never collide with anything else... The standard calls this feature protocol."
    - https://itnext.io/straits-9ef2b9a563cd
- [[t.cs.languages.GDScript]]
  - [Add a Trait system for GDScript](https://github.com/godotengine/godot-proposals/issues/6416)
- #scala 
  - but "Scala supports "traits", although these should have been called mixins (there is no explicit conflict resolution)." 
    - https://github.com/traitsjs/traits.js

### #c-sharp

- https://www.reddit.com/r/csharp/comments/7uc6dt/ive_created_a_mixin_library_for_c_and_would_like/
- [[prdct.partial-mixins]]
