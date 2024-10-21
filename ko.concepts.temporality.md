---
id: gevpci170z4xpynl0eyhkhf
title: Temporality
desc: ''
updated: 1729468979883
created: 1722876821821
---

## Thoughts

- maybe the triple format is not naturally up to the task of meta-modelled time
- 

### temporal-context

- calendar system
- time-slice granularity
- fluency approach?


### genesis-timestamp
  - has an associated store
  - naturally precise, but could be fuzzed 
  - universal (even if not recorded)
    - e.g. every keystroke has one, with a text editor (in-memory store)
  - context is real-world, digital, 
  - can be preserved or not across different stores
    - could be used for lineage
      - e.g. on every copy, the data adds a tx-ts+store-identifier
  - in RDF, a triple isn't enough (and using the graph in a quad wasteful) for expressing a transaction timestamp
    - so need to add a transaction-timestamp statement
    - but then you might go down an infinitely recursive rabbit hole of tx-timestamping the tx-timestamp statement 
      - maybe tx-ts triples are special, having a tx-ts equal to the tx-ts they encode
    - if you use [[ko.concepts.relator]] exclusively, you are golden
  - should be automated

### tombstone-timestamp 

- formery "invalidation-timestamp", but needed a new name, because it treads on valid-time

#### issues

- should be stored outside the relator/data because who's to say when a piece of data is dead?

#### uses

- for immutable contexts, expresses "not current"
  - can be complementary or an alternative to "[[ko.concepts.successor]]"?
  - corrections, like data-entry errors or buggy pipeline
- 



#### validity

- validity-start, valid-at, invalidity-start, invalid-at
  - only apply to relations
- abstractions shouldn't lose validity

- different kinds of validity
  - "in-world"/"in-application"
  - real-time
  - decision-time/assertion-time replaces transaction time because, for the most part, who cares when it was recorded in a store. 
    - mostly, assertion-time would be equal to transaction time, at least in a "live" system

#### immutability

- might be helpful to differentiate between corrections and updates, but that line is very thin and unstable, 
  - e.g. in a role-playing experience platform where in-world facts get bent/corrected and truth is more of a "what we decided worked best in the narrative"
  - i wanted to say abstractions are always true, but what about the case of corrections


## Prior Art

### 

![[ar.valid-time-rdf#instantiating-identifying-conceptrelationship-iir]]