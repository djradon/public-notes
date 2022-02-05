---
id: V5bZkKTrDG5cqo5NP5lBE
title: Kevin Feeny
desc: 'TerminusDB guy, Cliodynamicist and all round Data Obsessive'
updated: 1643809325310
created: 1643809159612
---

- [[p.hasURL]] https://medium.com/@kevin_10337

## [[soln.medium]]

- https://medium.com/terminusdb/graph-fundamentals-part-2-labelled-property-graphs-ba9a8edb5dfe
  - " RDF has a pure graph structure at a low-level but is often a confusing mess at a high level, while property graphs are the opposite"
  - jettisoning URLs in favor of local identifier becomes an ever more serious impediment — throwing away universal, uniform, dereferenceable identifiers in the age of the web looks less and less wise. 
  - "property graphs will likely fade out as knowledge graphs become adopted by enterprises and incorporated into their infrastructure — a well defined schema is not an optional"  
- https://medium.com/terminusdb/graph-fundamentals-part-3-graph-schema-languages-1fc25ca294dd
  - "class hierarchies and typed properties are by far the most useful and important mechanisms for defining the structure of a graph"
  - open-world assumption is problematic
- https://terminusdb.com/blog/graph-fundamentals-part-4-linked-data/
  - the big problem [with reusing terms from well-known vocabularies] is that the well-known ontologies and vocabularies such as foaf and dublin-core that have been reused, cannot really be used as libraries in such a manner. They lack precise and correct definitions and they are full of errors and mutual inconsistencies [1] and they themselves use terms from other ontologies — creating huge and unwieldy dependency trees. If, for example, we want to use the foaf ontology as a library, we need to also include several dozen dependant libraries, some of which no longer exist. So, the linked data approach, in fact, just uses these terms as untyped tags — there is no clear and usable definition of what any of these terms actually mean — people just bung in whatever they want — creating a situation where there are effectively no reliable semantics to any of these terms.
- https://medium.com/terminusdb/why-graph-will-win-703373bb5c41
  - Everything is pre-joined — you don’t have to disassemble objects into normalised tables and reassemble them with joins.
