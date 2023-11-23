---
id: 0446pg8cq2w5q4nibe9xp11
title: Mixin
desc: >-
  a class that contains methods for use by other classes without having to be
  the parent class of those other classes
updated: 1700153413586
created: 1696197242241
---

- [[c.comparable]] 
  - [[t.cs.entity-component-system]] [[t.cs.programming.code-reuse]]
  - [[t.cs.traits]]

## Issues

- where is the data? 

## [[p.supportedBy]]

- c# (since C# 8.0, by means of default methods of interfaces), but no data?
- scala Scala has a rich type system and Traits are a part of it which helps implement mixin behaviour.
  - but "Traits are Mixins just with some slightly different properties from a programming language designers point of view like Mixins require [[t.cs.sd.mixin.linearization]] while Traits are flattened and Traits traditionally don’t contain states."
- #rust Rust makes extensive use of mixins via traits. Traits, like in Scala, allow users to implement behaviours for a defined type. They are also used for generics and dynamic dispatch, which allow for types with same traits to be used interchangeably statically or dynamically at runtime respectively
- java default methods for interfaces (could work if every actor had a weak dictionary or whatever)
- javascript
  - https://javascript.info/mixins
```
// copy the methods
Object.assign(User.prototype, sayHiMixin);
```

## c.Implementation

- https://github.com/LokiMidgard/PartialMixins c#

## Resources

- https://stackoverflow.com/questions/255553/is-it-possible-to-implement-mixins-in-c / https://www.c-sharpcorner.com/UploadFile/b942f9/how-to-create-mixin-using-C-Sharp-4-0/
- https://www.reddit.com/r/csharp/comments/7uc6dt/ive_created_a_mixin_library_for_c_and_would_like/
- [The Power of Lua and Mixins](https://github.com/a327ex/blog/issues/2) ^wklu5ctv3kui
- https://stackoverflow.com/questions/28882903/uml-representation-of-php-trait