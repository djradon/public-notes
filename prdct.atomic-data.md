---
id: 13s2lqwflayx6ft508wgzpw
title: Atomic Data
desc: ''
updated: 1714117046903
created: 1714115290895
---

## Shortnames

### Advantages of Shortnames

Readability: Shortnames can make your transactions and queries more concise and easier to understand, especially when dealing with complex Property names.
Brevity: They reduce data size in transaction payloads.
Potential Namespace Management: Shortnames can play a role in how you manage namespaces within your data model.

### Important Considerations

- Name Collisions: Atomic Data guarantees uniqueness of the Subject-Property combination, mitigating shortname collisions within the context of an entity. However, if resources from multiple Classes with the same shortname are mixed, clients need a strategy to resolve potential clashes (see the Atomic Data FAQ you linked earlier).
- Not a Replacement for Full URIs: Shortnames are a convenience mechanism. Internally, Atomic Data still relies on full Property URIs.
- each Property URL must resolve to an online Atomic Data Property.