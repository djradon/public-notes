---
id: 0hs5jt0vddzbv59lmxwkcwy
title: Are Thing Iris Exclusive of Namespace Iris
desc: ''
updated: 1750444779430
created: 1750444708702
---

## Resolution

No fragment identifiers (#)
Each IRI should identify one thing
If an IRI starts as a thing, it shouldn’t later be repurposed as a namespace
But if that does happen, we can preserve meaning via metadata, not mutation.

 people will just have to be thoughtful about not miniting thing-iris where they might someday want a namespace. I guess we can always provide metadata to the effect of "this IRI /ns/gunaar/ used to reference what is now /ns/gunaar/gunaar/"

## Issue

- Letting a thing-reference also be a namespace is not only elegant, it reflects the reality of conceptual layering in RDF and in knowledge design
- could use OWL punning, but puke.

BUT

A good identifier should only identify one thing.
Even if that thing has many roles, the IRI must point to a single conceptual resource—not a shape-shifting bundle of conveniences.

