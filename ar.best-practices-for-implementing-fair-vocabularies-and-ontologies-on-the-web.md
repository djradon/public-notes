---
id: cbvo7vhvyzy57g5nyaawnzm
title: Best Practices for Implementing Fair Vocabularies and Ontologies on the Web
desc: ''
updated: 1727812352717
created: 1727808958884
---

- https://dgarijo.com/papers/best_practices2020.pdf
- authors: @daniel-garijo @maria-poveda-villalon
- keywords: [[t.km.ontology.metadata]] [[t.km.ontology.publication]] [[t.cs.data.fair]]

## Abstract

- With the adoption of Semantic Web technologies, an increas-
ing number of vocabularies and ontologies have been developed in differ-
ent domains, ranging from Biology to Agronomy or Geosciences. How-
ever, many of these ontologies are still difficult to find, access and un-
derstand by researchers due to a lack of documentation, URI resolving
issues, versioning problems, etc. In this chapter we describe guidelines
and best practices for creating accessible, understandable and reusable
ontologies on the Web, using standard practices and pointing to exist-
ing tools and frameworks developed by the Semantic Web community.
We illustrate our guidelines with concrete examples, in order to help
researchers implement these practices in their future vocabularies.


## Highlights

### Accessible Ontology URI Design

#### Ontology name and namespace prefix

- short and simple
- avoid overlapping with other existing vocabularie

#### Hash versus slash URIs

- using a slash allows treating each element of the ontology
as a separate entity that may be described in an independent manner.


#### Opaque URIs for classes and properties

- if we decide to change the name of the class in the future, the URI of the class would not be affected by it
  - t.2024.10.01.12 meh, just use an alias
- identifiers are language agnostic.
- The main drawback of using opaque URIs is the difficulty of interpreting properly classes and properties, which usually requires additional tooling for displaying the right labels. For this reason, we will not use them in our example 


#### Ontology versioning

- use semantic versioning
- It is discouraged to include version numbers as part of the ontology URI, as it would deeply affect interoperating with its instances.

#### Using permanent URIs

- There are several open, free services to create permanent URLs on the Web, among which purl.org12 (now hosted by the Internet Archive) and w3id13 (created by the W3C Permanent Identifier Community Group and supported by several companies)

### Generating Reusable Ontology Documentation

#### Ontology Metadata

- two main categories of metadata in an ontology: 
  - the metadata associated with the ontology itself 
  - the metadata associated with its elements (classes, object properties, datatype properties and individuals).

Table 1. Recommended and optional metadata for describing ontologies

Property name Annotation Property Rationale Guideline
License dcterms:license Usage conditions Recommended
Creator dcterms:creator Provenance and attribution Recommended
Contributor dcterms:contributor Provenance and attribution Recommended
Creation date dcterms:created Provenance Recommended
Previous version owl:priorVersion Provenance and comparison Recommended
Namespace URI vann:preferredNamespaceUri Identifying the ontology Recommended
Version IRI owl:versionIRI Versioning Recommended
Namespace prefix vann:preferredNamespacePrefix Identifying the ontology Recommended
Title dcterms:title Understanding Recommended
Description dcterms:description Understanding Recommended
Citation dcterms:bibliographicCitation Credit Recommended
Abstract dcterms:abstract Additional information Optional
See also rdfs:seeAlso Additional information Optional
Status sw:status Maturity information Optional
Backward compatibility owl:backwardCompatibleWith Version compatibility Optional
Incompatibility owl:incompatibleWith Version compatibility Optional
Modification date dcterms:modified Provenance and timeliness Optional
Issued date dcterms:issued Provenance and timeliness Optional
Source dcterms:source Provenance Optional
Publisher dcterms:published Provenance Optional
DOI bibo:doi Bibliographic information Optional
Logo foaf:logo Identifying the ontology Optional
Diagram foaf:depiction Visual documentation Optional


Table 2. Recommended and optional properties for describing ontology terms

Property name Annotation Property Rationale Guideline
Label rdfs:label Readibility Recommended
Definition rdfs:comment Understanding Recommended
Example vann:example Understanding Optional
Status sw:term status Understanding Optional
Rationale vaem:rationale Understanding Optional
Source dcterms:source Provenance Optional
Defined by rdfs:isDefinedBy Provenance Optional


#### Ontology Visualization

![](/assets/images/2024-10-01-12-13-49.png)

- in the last years, conventions for ontology diagrams have been proposed (e.g., [[VOWL|prdct.vowl]] [10] and [[Graffoo|prdct.graffoo]]21) but none have been standardized


### Ontology Publication on the Web

#### Ontology Accessibility in Multiple Interoperable Formats

- 303s (yech)
- "Here we expand these practices with our example ontology to illustrate: 1) How to support multiple serializations of an ontology (HTML and Turtle); 2) how to support version redirection, as we would like all the versions of the ontology to be appropriately available, not only the latest; 3) How to specify if a serial- ization is not supported (for example, requests for JSON-LD will return a 406 non-acceptable code, rather than an RDF/XML serialization); and 4) how to implement a default response in case the user agent doing the request does not specify a target in the request (by default we return Turtle)"

#### Making an Ontology Findable on the Web

1. Register the namespace prefix using prefix.cc,26 a crowdsourced registry where users can vote the most popular URI for a given prefix.
2. Register the ontology: There are a number of existing metadata registries that can be used for browsing existing ontologies [15][17]. Our recommenda- tion is to look first for domain-specific registries (e.g., Bioportal [17] in the biomedical domain, Agroportal [7] in Agronomy, etc.) commonly used by the target community of interest. When domain-specific registries do not exist, we suggest registering the ontology in a domain-generic metadata registry, such as Linked Open Vocabularies [15] (which has a manual curation process to ensure that minimum metadata is provided) or FAIRsharing.27
3. In-document annotations to help crawlers understand the metadata of the ontology when publishing it on the Web. These annotations can be added in your documentation through JSON-LD snippets,28 as shown below:


### Ontology Documentation and Publication Frameworks

- frameworks inspired by the continuous integration practices
in software engineering have arisen to support ontology engineering activities.
  -  offer end-to-end solutions that support ontology engineers documenting, visualizing, testing and publishing their ontologies; and we recom- mend them as an entry point to adopt some of the practices described in this chapter.
-  [[prdct.ontoology]]
-  [[prdct.vocol]]
-  [[prdct.pool-party]]
-  

### Conclusion

-In this chapter we have described implementation guidelines and recommen- dations for making ontologies findable (through metadata registries and anno- tations); accessible (through good practices in URI design and content nego- tiation), interoperable (showing how to serve ontologies in different standard serializations) and reusable (by describing the metadata and diagram guidelines needed for proper understanding) on the Web while following the Linked Data principles