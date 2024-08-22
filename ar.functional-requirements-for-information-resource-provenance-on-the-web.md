---
id: pj7hxg43l92nle5z806eax9
title: Functional Requirements for Information Resource Provenance on the Web
desc: ''
updated: 1724282047601
created: 1724269000035
---

- https://link.springer.com/chapter/10.1007/978-3-642-34222-6_5
- topic: [[prdct.functional-requirements-for-information-resources-frir]]
- authors: @jamie-mccusker @deborah-mcguinness


## Highlights

### The Semiotics of HTTP URLs

![](/assets/images/2024-08-21-12-51-39.png)

-  the document retrieved cannot be defined only as a representation of a resource
   -  The document can be described in terms of either its content or the set of bytes used to represent it – or both ^w1t3fxtaiozl
   
### FRBR and FRIR

![[prdct.frbr#^kph9708t2eod]]

- Functional Requirements for Information Resources5 (FRIR) extends the use of frbr:Work, frbr:Expression, frbr:Manifestation, and frbr:Item to electronic resources, and therefore any information resource. 
- a frbr:Work remains a distinct intellectual or artistic creation. 
  - A frbr:Work corresponds to the Resource or Referent in the semiotic framework discussed above, and is identified by a URL, as was shown in Figure 2
- frbr:Expression corresponds to a specific set of content regardless of its serialization.
  - For instance, two files would have the same frbr:Expression if they are the same picture stored in two different formats
    - t.2024.08.21.15 this is a bit blurry, but a Turtle and JSON-LD could be expressions of the same ontology
- frbr:Manifestations correspond to a specific bit pattern. If a file is an exact copy of another file, they have the same frbr:Manifestation.
- An frbr:Item is a specific copy of information stored somewhere or transmitted through a communication link. If a copy of the frbr:Item is made, it results in a new frbr:Item.
- FRIR also integrates FRBR with the W3C Provenance Ontology (PROV-O) by declaring frbr:Endeavour to be a subclass of prov:Entity and mapping 14 of 18 frbr:relatedEndeavour subproperties as subproperties of one or more of prov:wasDerivedFrom, prov:alternateOf, and prov:specializationOf, as shown in Figure 3.

![](/assets/images/2024-08-21-12-56-17.png)

- As part of FRIR we have identified two levels of cryptographically computable identity: content and message.
  - Conventional message digests correspond to frbr:Manifestation
  - content digests correspond to frbr:Expressions
    - content digests have been developed for RDF graphs, spreadsheets, images, and XML documents that provide the same digest hash regardless of any particular serialization

### Explaining HTTP with FRBR, FRIR, and PROV-O

- n.b.: two identifiers can potentially denote the same thing, e.g. a mirror is the same work
  - t.2024.08.21.15 it's an interesting case when a single identifier can identify a work, an expression, a manifestation, and arguably an item.
- We uniquely identify the data streamed over a particular HTTP transaction using the combined message digest of the HTTP header and content.
- This enables provenance trace assertions to be applied to individual HTTP transactions without having to store the entire transaction.

## Implementation

- https://github.com/timrdf/csv2rdf4lod-automation/wiki/Script:-pcurl.py
  - uses [[prdct.nepomuk-file-ontology-nfo]]
