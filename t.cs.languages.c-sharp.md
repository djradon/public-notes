---
id: 2MYxIAcVjpPWRLiA3DDtT
title: C#
desc: ''
updated: 1708905092417
created: 1638152505835
---


## Tips

### public fields

- - "no fields should ever be non-private. I'll make a small exception for static readonly fields such as string.Empty, but that's (nearly) all."


### settable properties and public fields

- A property communicates the idea of "I will make a value available to you, or accept a value from you." It's not an implementation concept, it's an interface concept. A field, on the other hand, communicates the implementation - it says "this type represents a value in this very specific way".

## Resources

- https://itnext.io/getting-functional-with-c-6c74bf279616

## Referebces

- https://csharpindepth.com/articles/PropertiesMatter
