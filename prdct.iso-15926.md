---
id: 4y6z8pa7c9s27siifxar3rc
title: ISO 15926
desc: ''
updated: 1721687394016
created: 1721686967873
---

- http://rds.posccaesar.org/2008/07/OWL/ISO-15926-2_2003_annotations

### Description

- relies on a so-called 4D top-level ontology.
  - " it admits the existence of events (things that necessarily exist and develop in time) but not of objects as traditionally understood."


### Workaround: The OWL List ontology[](https://rds.posccaesar.org/doc/background/iso15926-2_in_OWL//#workaround-the-owl-list-ontology)

The ISO 15926-2 OWL rendering imports the _OWL List_ ontology, which is no longer available from its original location at `www.co-ode.org`, and Protégé will display the following warning. Unless you have a local copy available, select “No”. The absence of OWL lists only affects the ISO 15926-2 entity types [MultidimensionalObject](http://rds.posccaesar.org/2008/02/OWL/ISO-15926-2_2003#MultidimensionalObject) and [ClassOfMultidimensionalObject](http://rds.posccaesar.org/2008/02/OWL/ISO-15926-2_2003#ClassOfMultidimensionalObject).


A replacement for the OWL List ontology is available at [https://w3id.org/list](https://w3id.org/list), although with a different namespace (2015).

## References

- https://rds.posccaesar.org/doc/background/iso15926-2_in_OWL/
- [[ar.some-open-issues-after-twenty-years-of-formal-ontology]]