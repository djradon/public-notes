---
id: pi9eqxk27aaedm6ae8tn180
title: DCAT Data Catalog
desc: >-
  provides RDF classes and properties to allow datasets and data services to be
  described and included in a catalog
updated: 1729274827902
created: 1721241717863
---

- https://www.w3.org/TR/vocab-dcat/

## Features

- DCAT does not make any assumptions about [the various] serialization formats of the datasets but it does distinguish between the abstract dataset and its different manifestations or distributions
- defines a relatively comprehensive set of reusable terms from established vocabularies (Dublin Core, SKOS, FOAF, PROV) and extends these with some integrating classes and missing properties.

## Terms

- **dcat:Catalog**: a dataset in which each individual item is a metadata record describing datasets and data services
- **dcat:Resource**: not intended to be used directly, but is the parent class of dcat:Dataset, dcat:DataService and dcat:Catalog

### Spatiotemporal terms

distribution
frequency
spatial/geographic coverage
spatial resolution

#### dct:temporal (temporal coverage)

#### 	dcat:temporalResolution

intended to provide a summary indication of the temporal resolution of the data distribution as a single value. More complex descriptions of various aspects of temporal precision, accuracy, resolution and other statistics can be provided using the Data Quality Vocabulary [VOCAB-DQV](https://www.w3.org/TR/vocab-dcat/#Property:dataset_distribution#bib-vocab-dqv) "Data on the Web Best Practices: Data Quality Vocabulary".

#### prov:wasGeneratedBy


## References

