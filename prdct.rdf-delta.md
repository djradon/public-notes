---
id: djudnp9uyqjmo1gltkjhcv6
title: Rdf Delta
desc: ''
updated: 1728597055987
created: 1714229209148
---

- https://afs.github.io/rdf-delta/
- different-from: [[ar.delta-an-ontology-for-the-distribution-of-differences-between-rdf-graphs]]
- supports: [[prdct.rdf-thrift]]

## Summary

- RDF patch is a format for recording changes to an RDF Dataset
- an evolution of the original RDF Patch described in https://afs.github.io/rdf-delta/rdf-patch.html
- Abort, TA is provided so that changes can be streamed, not obliging the application to buffer change and wait to confirm the action is committed.

### Two aspects

Distributing changes to a dataset has two aspects: the format used to record changes and the mechanism used to propagate changes.

RDF Delta provides these into two parts:

    RDF Patch - a format to record changes that is easy to generate and consume.
    RDF Patch Logs - a protocol for distributing change files.

## Issues

- There is only a single copy of the patch store and any file storage may be lost so it is better to highly reliable file system where possible.
  - The patch store can be backed up by backing up the PatchStore directory when the server is not in-use.

## References

