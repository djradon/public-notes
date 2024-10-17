---
id: lsqn84g8faksg2jxvbj9e1f
title: JSON-AD
desc: 'atomic data'
updated: 1729151010579
created: 1710789774943
---

- similar: [[prdct.hextuples]]
- use_case: Use JSON-AD if you don't have to support existing RDF data, but do value JSON compatibility and type safety.
- creator: @joep-meindertsma
- complementary: [[prdct.astro]]

## Description

[JSON-AD](https://docs.atomicdata.dev/core/json-ad.html) (JSON Atomic Data) only supports a strict subset of RDF, so it is an odd one in this list. In other words: it cannot be used to serialize all existing RDF data. However, because it allows only a strict subset, it also has a couple of advantages over other formats:

-   Very **low parsing cost / high performance**. It can be parsed as plain JSON, which means that many efficient and performant parsers are available.
-   **Easy to understand**. Since it supports only a subset of RDF, it doesn't suffer from some of the [quirks of RDF](https://docs.atomicdata.dev/interoperability/rdf.html) such as predicate-non-uniqueness
-   It supports **native JSON arrays** as collections, which prevents the complexities of dealing with [ordered data in RDF](https://ontola.io/blog/ordered-data-in-rdf/).
    -   t.2024.05.27.12 but if you can't represent ordered colelctions easily in RDF, it's not a strict subset
-   **Type safety**. Each key in a JSON-AD object should resolve to a [Property](https://atomicdata.dev/classes/Property), which describes [datatype](https://atomicdata.dev/properties/datatype) and [description](https://atomicdata.dev/properties/description).

Here's the `description` Property from above, serialized as JSON-AD:

![](/assets/images/2024-06-10-15-12-38.png)

Because these properties also have [`shortnames`](https://atomicdata.dev/properties/shortname), we can easily [serialize Atomic Data to plain JSON](https://docs.atomicdata.dev/interoperability/json.html), without the long URLS:

![](/assets/images/2024-06-10-15-10-34.png)

## Issues

- something about shortnames
- Atomic only allows those who control a resource's subject URL endpoint to edit the data. This means that you can't add triples about something that you don't control.

## References

- https://ontola.io/blog/rdf-serialization-formats