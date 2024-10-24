---
id: imx167fidgm5kg7qht8lkh2
title: Kosmion Log
desc: ''
updated: 1729047676451
created: 1723147341720
---

## t.2024.08.08.13

- "micro-graph" approach, where each relator is its own named graph, might have some benefits
  - maybe you could preserve (some of) the classic S-P-O approach, layering on @christopher-welty's Ontology for Fluents


- [x] regarding [[prdct.ontogen]], is it at odds with keeping history (of events, relator validity) in the dataset? i.e., RDF immutability or event-driven/relator-based RDF 
  - see [[pub.question-log.2024.08.16.ontogen-vs-relator-based-rdf]]
  - graph-based versioning might be orthogonal to an immutable-ish data store (in text files, in git)

# t.2024.08.17.12

- everything that exists has some physical aspect, but some physical systems have sub-systems that support "aphysical (supra-physical) things", and it can be useful to speak of those as universes of their own and abstract away the "physical-prime" context (that is kinda boring because it subsumes everything else). Call them supra-universes or subcontexts, eg., a functioning brain, an operating computer, a networked game.
- versioning everywhere... major signals breaking change, so there's value in using the major version with no minor specific as an alias to "latest minor"
- there's value in aliasing your ontology to other used ontologies... avoids a profusion of namespacing. Maybe you don't like that other guy's uptime or prefix choices
- how much of starting with a conventional ontology leak into [[ko.concepts.relator]]-based predication. 
- as long as the reference is unique, you can do nice aliasing that cuts through 
  - [ ] could do aliasing in RDF... maybe just an import statement pointing to current version.

## t.2024.08.17.13

- holonic RDF, where each level of aggregation gets its own versioning
  - used-version
  - WHAT WAS that [[ar.w3.cool-uris]] tech for appending stuff

## t.2024.10.11.12

- using [[prdct.unified-foundational-ontology.gUFO]] as a guide, my head is starting to swim.  

## t.2024.10.13.07

- [[prdct.prov-o]] has `qualifiedInfluence` and its subproperties:
  - prov:qualifiedAssociation
  - prov:qualifiedRevision
  - prov:qualifiedInvalidation
  - prov:qualifiedPrimarySource
  - prov:qualifiedDerivation
  - prov:qualifiedGeneration
  - prov:qualifiedUsage
  - prov:qualifiedQuotation
  - prov:qualifiedStart
  - prov:qualifiedAttribution
  - prov:qualifiedEnd
  - prov:qualifiedCommunication
  - prov:qualifiedDelegation


## t.2024.10.15.11

- RelatorCatalog per entity collects all the RelatorSets, which are datasets where the default graph (mutable) points to the immutable named graphs. 
  - pointer isn't strictly necessary, but might speed querying, aid distribution-packing, or be used for consistency checking
- damn, brain not working, why did we need a catalog of relatorsets?
  - well, all the info about an entity might be split across different datasets. 
  - the fact that there's not an inverse property for dcat:dataset might be a hint, but it seems like data should be allowed to join itself? 
- Another reason for separating names from downloadURLs, you might want to shadow-recreate something on your own (or with local files)

## t.2024.10.15.12

- using IRI refs instead of anyURI helps clear the clutter, but maybe there'd be cases where you want to preserve a sourceURL and change the prefix
- things aren't literally immutable in github, but quasi-immutability (aka stable) is better... allows you to preserve history but take out PI, typos, and embarassments.
- for concision, maybe the "current relator" gets duplicated into the placeholder/primary entity?
- it makes sense to be able to come at things from both ways, with atoms making claims on collectives/entities. named graphs as atoms probably makes the most sense.
- atomicity is a facit.
  - datatype-property-carrying
- conventional RDF, esp. class hierarchy, only for interfacing with RDF and owl: only for owl.
- ethos is: it's just guidelines. so lots of things should be in the 

## t.2024.10.15.16

- http://www.w3.org/ns/prov#Agent should be a sublass of Entity? Or mayb eit doesn't matter. 
- probably I just just go for it, make kosm: the one stop shop for fixing everyone else's issues and integrating it. A ruthless and misleading-ish approach would be to steal the most popular terms.
  - review 'em for
    - domain and range are reasonable
    - document is literal, sense is IRI.
      - could use a new datatype for IRI that includes folder hierarchy pattern matching, I guess I can leave that to the computers to develop. we're just at v0 buddy.
- is the time to modularize: right from the start?
- full, core, facet-stereotypes, borrowed terms/mnemonic forks.
- can you make a property's subproperty require different things
  - e.g downloadURL, homepageURL, et al subproperty downloadIRI. ie.., a superproperty for objectprop/dataprop
- it's going to be so great, you'll want to use quasi-immutable, facet-oriented RDF for your ontologies too.
- make two versions avail, one with owl:includes, or rather kosm:includes means the same thing 
- everything is a data catalog, or rather, every decent (kosmethodology-compliant entity) is


## t.2024.10.24.06

- maybe a "semantic repo" is the top-level concept, with:
  - ns/entity
  - ns/graph
  - ns/dataset
  - ns/catalog
  - 