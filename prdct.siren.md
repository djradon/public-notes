---
id: tgh7j75z4db4fxrf6tyfibq
title: Siren
desc: 'a hypermedia specification for representing entities'
updated: 1716834802505
created: 1714750445287
---

- dead since 2000
- repo: https://github.com/kevinswiber/siren

![[prdct.hydra#similar]]

## Features

- Actions show available behaviors an entity exposes.
- Siren also has a concept of "class." The class attribute may contain multiple descriptors of the current representation. I've avoided calling these "type descriptors." They act more like "mixin descriptors" (i.e., if an entity is of a certain class, it may have properties, actions, sub-entities, or links associated with it). When layering a UI on top of Siren, I've also used the class attribute to act as a view router (e.g., When a representation comes back with an "error" class, route to the error view or when a representation contains a "home" class, route to the home view... or some combination... When a representation has both the "home" and "error" classes, display the error alongside the home view.) 

## Comparisons

### Siren vs Hydra

- "Before Hydra, Siren was perceived as being the most complex JSON-based hypermedia format.  And now, I think, Hydra has taken over that label."
- 


## References

- https://lists.w3.org/Archives/Public/public-hydra/2016Jan/0026.html
- https://github.com/kevinswiber/siren/issues/15