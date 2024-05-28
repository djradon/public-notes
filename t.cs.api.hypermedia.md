---
id: bc2ya18buka4rr2qycn4l5m
title: Hypermedia APIs
desc: ''
updated: 1716911129437
created: 1701294427191
alias: hateoas
---

## Related


- [[t.cs.web.hateoas]]

## Everything as a Resource

-   **Data model as a resource**: Describing the data model as a resource could help build forms for entering data or interactive user interfaces. One vocabulary to assist here is the SHACL Shapes Constraint Language for describing graph data structures.
-   **Hypermedia as a resource**: The API itself can be described as a resource too. One way to do this is using [Hydra](https://nordicapis.com/hydra-for-hypermedia-apis-benefits-components-and-examples/), a vocabulary for describing APIs with RDF. This sort of self-documentation is similar to OpenAPI but could make the API discoverable at runtime.
-   **Access control as a resource**: The [Basic Access Control ontology](https://lov.linkeddata.es/dataset/lov/vocabs/acl) is another shared vocabulary for describing access control that was [proposed by none other than Tim Berners-Lee](https://dig.csail.mit.edu/2009/Papers/ISWC/rdf-access-control/paper.pdf).

## Solutions

- [[prdct.hydra]]
- [[prdct.json.hyper-schema]]
- [[prdct.siren]]
- [[prdct.HAL]]

## Comparisons

### Hypermedia APIs vs. Data APIs

Hypermedia APIs:

-   Will be trivially [REST-ful](https://en.wikipedia.org/wiki/Representational_state_transfer), since they are simply what [Roy Fielding was describing](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).
-   Should be driven by the needs of the underlying hypermedia application
-   May change dramatically _without_ versioning information, because hypermedia utilizes [self describing messages](https://en.wikipedia.org/wiki/Representational_state_transfer#Uniform_interface)
-   Should be passed directly to humans, to maximize the flexibility of the system

Data APIs, on the other hand:

-   Will not benefit dramatically from REST-fulness, beyond perhaps [Level 2 of the Richardson Maturity Model](https://en.wikipedia.org/wiki/Richardson_Maturity_Model)
-   Should strive for both regularity and expressiveness due to the arbitrary data needs of consumers
-   Should be versioned and should be very stable within a particular version of the API
-   Should be consumed by code, processed and then potentially presented to a human

## References

- https://nordicapis.com/exploring-the-hidden-powers-of-hypermedia/
- https://htmx.org/essays/hypermedia-apis-vs-data-apis/