---
id: HwnGpcj6H3ZfGO8AFgLxO
title: Composition Alone Cant Replace Inheritance
desc: ''
updated: 1696287929570
created: 1637123039733
---


- [[p.hasURL]] https://javascript.plainenglish.io/composition-alone-cant-replace-inheritance-606760f03d60
- [[p.hasTopic]] #javascript [[t.cs.programming.code-reuse]]
- [[p.hasSummaryPoints]]
  - Sometimes, you simply want to have all of your shared methods exist flat on the same object as you would get with inheritance.
    - But with P.A.I.L restrictions: 
      - private
        - You are using inheritance purely for code reuse, not for public hierarchies.
      - base classes abstract
      - Isolate your base and child classes. Your base and child classes should be completely oblivious of the properties the other class provides. A child class should never override a base class’s methods or even access a property inherited from the base class, and a base class should never expect a child class to provide a missing method implementation
      - last resort. Only use restricted inheritance when no other options are good enough. Inheritance should be a dusty tool in the far corner of your tool shed

