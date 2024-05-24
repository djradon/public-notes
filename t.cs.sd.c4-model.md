---
id: DyUK7zKrSwEaMNvad3NYh
title: C4 Model
desc: 'model a software system, at various levels of abstraction (context, containers, components and code)'
updated: 1716531692961
created: 1645831289441
---

- [[p.hasURL]] https://c4model.com/

## Solutions
  - [[prdct.structurizr]]
  - [[prdct.c4-plantuml]]
  - [[prdct.icepanel]]
  - [[prdct.carbide]]
  - 

- [[p.hasHighlight]]
  -  To document a library, framework or SDK, you might be better off using something like UML
  -  Sometimes diagrams work better showing dependency relationships (e.g. uses, reads from, etc), and sometimes data flow (e.g. customer update events) works better.
     -  most relationships can be expressed either way, and the more explicit you can be, the better. For example, describing a relationship as "sends customer update events to" can be more descriptive than simply "customer update events". 
-  

## Comparison

![[prdct.ilograph#concrete-vs-abstract-models]]

## Questions 

### "is X a container or a component?".

## Issues

### Overly-prescriptive abstractions

- using domain-specific abstractions makes more sense than using arbitrary ones. Diagram authors benefit from thinking about each system on its own terms (and in its own terms). Diagram viewers do, too.
- The top-down, abstraction-first approach of C4 risks focusing too much on a system’s abstractions at the expense of its concrete resources.


### Product Selector

- https://c4model.com/ 

- [[c.resource]]
  - https://alpha2phi.medium.com/code-based-diagramming-6b1bcc732aab
  - https://c4model.com/
    - [[p.mentioned]]
      - [[prdct.model]]
      - [[prdct.pumla]]
      - [[prdct.rdb-model]]
      - 

## References

- https://www.ilograph.com/blog/posts/concrete-diagramming-models/
- https://www.reddit.com/r/softwarearchitecture/comments/16upcj2/dynamic_nested_diagram_for_software_architecture/
- https://medium.com/nick-tune-tech-strategy-blog/domain-driven-architecture-diagrams-139a75acb578