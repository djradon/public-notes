---
id: 0dohrn5qvxfx1vys0qusuky
title: Getting_started_with_fluree
desc: ''
updated: 1701968488908
created: 1701965208506
hosted_by: @brian-platz
presenters: @kevin-doubleday @andrew_johnson
topics: 
  - "[[prdct.fluree.nexus]]"
  - 
---


- Use of Data is evolving
  - Solution: Collaborative Data Network
  - semantics of data shouldn't sit in the app
  - web3 semantics standards (rdf, owl, shacl); [[t.km.knowledge-graph]] [[c.Software.Database.Graph.Property]]; [[prdct.JSON-LD]]; [[prdct.fluree.flureeql]]
  - decentralization
    - cryptographically provable identities
    - real-time distributed ledgers
    - trustless
    - programmable logic (i.e., [[t.cs.blockchain.contracts]]
      -  "much of programmability can be contained in the data and its constraints"
  - ![](/assets/images/2023-12-07-08-10-51.png))
  - [[t.cs.data.time-travel]]
- Collaboration
  - Fluree's immutability allows rewind
  - Compose Queries across data
  - future: reasoning and inferencing


## Questions

- Q: how do you represent relations, ie. object properties
  - A: Here's a link to this in our docs, David! https://developers.flur.ee/docs/learn/tutorial/working-with-graph-data/#graph-crawling-in-our-select-clauses
- Q: can @type have multiple keys, i.e., multiple inheritance/class-membership
  - A: Yes absolutely! Any instance can explicitly belong to multiple types, and inheritance can be multi-tiered
- no need for [[t.cs.data.object-relational-mapping]]
- Q: do you see a need for some kind of object mapping SDK for marshalling data into code? maybe you have recommendation for existing json-to-plain-old-*-objects libraries?
  - A: It depends on your programming language as to if this is desirable or not. Many today are very comfortable working directly with data structures as a first-class citizen, but we may have some speciifc library support for languages that very object-centric. Even something like Java would be fairly easy to have a contructor to put JSON into an object without a library hopefully.
- Q: There's Time-Travel support for "Transaction Time", but do you have any thoughts about time-travel for "valid time", aka 

### Other people's questions

- Q: the current example seems related to foaf ontology, do you have predefined vocabularies available like vcard, dc, skos, etc?, or do we have to include them from scratch?
  - A: The demo isn't using any pre-defined vocabulary, but absolutely can use any RDF-based ontology. Inferencing is largely limited today to RDFS-based descriptions, but we do have some limited OWL-based ontology support which I mentioned will be much more broad shortly (and in a very unique Fluree-like way).
- Q: is there support for delegation/policy chains? For example: Person A has created the database. Person B gets read and write access to entity type A and B. In the case of a delegation chain; person B would be able to give (a subset of) the rights to what it can do to yet another person
  - A: Since policies are data, you can make policies about policies
- Q: Access control?
  - A: REBAC: relationship-based access control
    - simple rules
  - A: multiple policy groups are "only one has to succeed" but you can express AND conditions