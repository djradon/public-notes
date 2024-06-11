---
id: xqyv74byikdfixf87o22lcq
title: HexTuples
desc: ''
updated: 1718062367295
created: 1710789855342
---

- similar: [[prdct.thrift.rdf-binary]]
- based-on: [[prdct.ndjson]]

## Description

HexTuples is an NDJSON (Newline Delimited JSON) based RDF serialization format. It is designed to achieve the best possible performance in a JS context (i.e. the browser). It uses plain JSON arrays, in which the position of the items denote subject, predicate, object, datatype, lang and graph.

["https://www.w3.org/People/Berners-Lee/", "http://schema.org/birthDate", "1955-06-08", "http://www.w3.org/2001/XMLSchema#date", "", ""]
["https://www.w3.org/People/Berners-Lee/", "http://schema.org/birthPlace", "http://dbpedia.org/resource/London", "http://www.w3.org/1999/02/22-rdf-syntax-ns#namedNode", "", ""]

HexTuples is designed by Thom van Kalkeren (a colleague of mine) because he noticed that parsing / serialization was unnecessarily costly in our stack, even when using the relatively performant n-quads format. Since HexTuples is serialized in NDJSON, it benefits from the highly optimized JSON parsers in browsers. It uses NDJSON instead of regular JSON because it makes it easier to parse concatenated responses (multiple root objects in one document). As an added plus, this enables streaming parsing as well, which gives it another performance boost. Our JS RDF libraries (link-lib, link-redux) have an internal RDF graph model which uses these arrays as well, which means that there is minimal mapping cost when parsing Hex-Tuple statements. This format is especially suitable for real front-end applications that use dynamic RDF data.

## References

- https://ontola.io/blog/rdf-serialization-formats