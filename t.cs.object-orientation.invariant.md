---
id: 187lmw9ze1l2gkgpfg8dc36
title: Invariant
desc: 'a set of assertions that must always hold true during the life of an object for the program to be valid.'
updated: 1696710271229
created: 1696710118799
---

- #description a set of assertions that must always hold true during the life of an object for the program to be valid.
- #eg An example of invariant could be that exactly one of two member variables should be null. Or that if one has a given value, then the set of allowed values for the other is this or that...
- [[c.pattern]] I sometime use a member function of the object to check that the invariant holds. If this is not the case, an assert is raised. And the method is called at the start and exit of each method that changes the object (in C++, this is only one line...)

## Resources

- https://softwareengineering.stackexchange.com/questions/32727/what-are-invariants-how-can-they-be-used-and-have-you-ever-used-it-in-your-pro