---
id: 54xs03d1txghek4nv0fwqo2
title: V3
desc: ''
updated: 1723829691892
created: 1721429380319
---

## Features

### Versioning

- In DCAT 3 (Data Catalog Vocabulary version 3), versioning is managed using properties that allow you to describe different versions of datasets, distributions, and other cataloged resources. Specifically, DCAT 3 introduces the `dcterms:hasVersion`, `dcterms:isVersionOf`, and `adms:versionNotes` properties to indicate relationships between versions, and to describe changes across versions.
- This enables users to track the evolution of datasets and maintain a clear history of modifications, ensuring that consumers of the data are aware of its version history and any updates that have occurred.

## Example

```turtle
ex:catalog
  a dcat:Catalog ;
  dcterms:title "Imaginary Catalog"@en ;
  dcterms:title "Catálogo imaginario"@es ;
  rdfs:label "Imaginary Catalog"@en ;
  rdfs:label "Catálogo imaginario"@es ;
  foaf:homepage <http://dcat.example.org/catalog> ;
  dcterms:publisher ex:transparency-office ;
  dcterms:language <http://id.loc.gov/vocabulary/iso639-1/en>  ;
  dcat:dataset ex:dataset-001 , ex:dataset-002 , ex:dataset-003 ;
  .
```
