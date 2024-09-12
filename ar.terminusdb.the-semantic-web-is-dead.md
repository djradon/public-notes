---
id: 5zyylmcf3pq14viy68mzbde
title: The Semantic Web Is Dead
desc: ''
updated: 1726179310431
created: 1726163392889
---

- https://terminusdb.com/blog/the-semantic-web-is-dead/
- author: @gavin-mendel-gleason
- mentions: 
  - [[t.phil.logic.doxastic]]
  - [[ar.elaboration-in-dependent-type-theory]]

## Highlights

### Issues

- no unique name assumption
  - "Aliasing is a nightmare, computationally expensive, and leads to difficult-to-understand reasoning."
- [[t.cs.web.w3c.rdf.open-world-assumption]]
- "things are too far apart": class definitions require "lots of separately defined properties, each of which is verbose. When you add restrictions to them it becomes even worse"
- "polluting the data with inference"
  - "In [[prdct.owl]] we entail things into the graph which then looks just like the data from which it was entailed."
  - "The dream of computers that reasoned about data as it arrived to create some great symbolic AI, without a Doxastic approach is frankly silly."
    - t.2024.09.12.15 so take a doxastatic approach!
- "Not much in the way of useable constraints, sorry"
  - [[prdct.shacl]] goes a long way to alleviating this problem with OWL, but then it doesn’t replace OWL. Instead of giving us a schematic ontology language, we are left with two different languages which must now be kept in sync.

### The Right Way

- "Instead of all of this complexity, we should just have a standard schema language, which can be written in JSON or YAML. It should allow us to describe all of the data models in human language. It should make it easy for this to be internationalized."
- "What we need is a Literate Type Theory for JSON, which allows us to specify typed references"

## References

- https://www.reddit.com/r/semanticweb/comments/wkz8un/the_semantic_web_is_dead_long_live_the_semantic/