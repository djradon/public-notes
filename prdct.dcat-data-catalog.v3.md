---
id: 54xs03d1txghek4nv0fwqo2
title: DCATv3
desc: ''
updated: 1729977018884
created: 1721429380319
---

## Features

### Versioning

- In DCAT 3 (Data Catalog Vocabulary version 3), versioning is managed using properties that allow you to describe different versions of datasets, distributions, and other cataloged resources. Specifically, DCAT 3 introduces the `dcterms:hasVersion`, `dcterms:isVersionOf`, and `adms:versionNotes` properties to indicate relationships between versions, and to describe changes across versions.
- This enables users to track the evolution of datasets and maintain a clear history of modifications, ensuring that consumers of the data are aware of its version history and any updates that have occurred.

### Dataset Series

- DCAT makes dataset series first class citizens of data catalogs by minting a new class dcat:DatasetSeries, defined as a subclass of dcat:Dataset. The datasets are linked to the dataset series by using the property dcat:inSeries. Note that a dataset series can also be hierarchical, and a dataset series can be a member of another dataset series.
- see [[community.github.w3c.dxwg.issues.868]] and [[community.github.w3c.dxwg.issues.1409-using-dcat-next-and-dcat-version-in-dataseries]]
- dcat:inSeries 

### 7. Use of inverse properties

The properties described in 6. Vocabulary specification do not include inverses intentionally, with the purpose of ensuring interoperability also in systems not making use of OWL reasoning.

However, recognizing that inverses are needed for some use cases, DCAT supports them, but with the requirement that they MAY be used only in addition to those described in 6. Vocabulary specification, and that they MUST NOT be used to replace them.

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

ex:dataset-001
  a dcat:Dataset ;
  dcterms:title "Imaginary dataset"@en ;
  dcterms:title "Conjunto de datos imaginario"@es ;
  dcat:keyword "accountability"@en, "transparency"@en, "payments"@en ;
  dcat:keyword "responsabilidad"@es, "transparencia"@es, "pagos"@es ;
  dcterms:creator ex:finance-employee-001 ;
  dcterms:issued "2011-12-05"^^xsd:date ;
  dcterms:modified "2011-12-15"^^xsd:date ;
  dcat:contactPoint <http://dcat.example.org/transparency-office/contact> ;
  dcterms:temporal [ a dcterms:PeriodOfTime ;
    dcat:startDate "2011-07-01"^^xsd:date ; 
    dcat:endDate   "2011-09-30"^^xsd:date ;
  ];
  dcat:temporalResolution "P1D"^^xsd:duration ;
  dcterms:spatial <http://sws.geonames.org/6695072/> ;
  dcat:spatialResolutionInMeters "30.0"^^xsd:decimal ;
  dcterms:publisher ex:finance-ministry ;
  dcterms:language <http://id.loc.gov/vocabulary/iso639-1/en> ;
  dcterms:accrualPeriodicity <http://purl.org/linked-data/sdmx/2009/code#freq-W>  ;
  dcat:distribution ex:dataset-001-csv ;
  .

ex:dataset-001-csv
  a dcat:Distribution ;
  dcat:downloadURL <http://dcat.example.org/files/001.csv> ;
  dcterms:title "CSV distribution of imaginary dataset 001"@en ;
  dcterms:title "distribución en CSV del conjunto de datos imaginario 001"@es ;
  dcat:mediaType <http://www.iana.org/assignments/media-types/text/csv> ;
  dcat:byteSize "5120"^^xsd:nonNegativeInteger ;
  .
```

## References

- [[prdct.provencance-authoring-versioning-ontology-pav]]