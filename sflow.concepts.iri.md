---
id: eo43ueh0viren1xkjcjregc
title: Semantic Flow IRIs
desc: ''
updated: 1750372560358
created: 1750368774797
---

# Semantic Flow & IRI Schema Context Summary

## Project Overview
**Semantic Flow (sflow)** is an ambitious system for publishing semantic data with complete version history using GitHub infrastructure. It aims to solve the problem of evolving graph data by providing immutable versioning while maintaining dereferenceable IRIs.

**Key Innovation**: Every IRI becomes dereferenceable, creating a comprehensive semantic web where any resource can be explored.

## Core Architecture

### IRI Types (5 categories)
1. **IRIs that refer to non-datasets** (things) - not versioned
2. **IRIs that refer to dataset series** (DSS) - not versioned, but contain versioned datasets  
3. **IRIs that refer to datasets** (versioned) - immutable snapshots
4. **IRIs that are HTML pages** - `index.html` files for human consumption
5. **IRIs that are distributions** - RDF files (`.trig`, `.jsonld`, etc.)

### URL Pattern Semantics
- **Trailing slash** (`/`) = "refers" (abstract entities, series, concepts)
- **Filename** = "is" (concrete files, distributions, pages)

Example:
- `ns/dave-richardson/` = refers to Dave the person
- `ns/dave-richardson/index.html` = is the HTML page about Dave
- `ns/_series/personal-info/v3/personal-info_v3.trig` = is the RDF file

### Three-Way Recursive Namespace Division
Every folder at any level is one of three types:

1. **Sub-namespace** - contains other folders following the same pattern
2. **Thing identifier** - terminal folder with `index.html` and `_catalog/`
3. **`_series/`** - contains dataset series with `v*` versioning subfolders

```
ns/
├── _catalog/                 # catalog DSS for namespace
│   ├── v1/, v2/, _next/
├── people/                   # sub-namespace
│   ├── _catalog/            # catalog DSS for people namespace
│   ├── _series/             # dataset series container
│   │   └── all-people/      # specific dataset series
│   │       ├── v1/, v2/, _next/
│   └── dave-richardson/     # thing identifier (terminal)
│       ├── index.html
│       └── _catalog/        # catalog DSS for Dave
└── concepts/                # sub-namespace
    └── friendship/          # thing identifier
```

## Key Constraints & Rules

### File Organization
- **Thing folders**: Only `index.html` and `_catalog/` (no subfolders)
- **Series folders**: Only `v*`, `_next`, `_catalog/` (no other subfolders)
- **RDF files**: Only exist in `v*` version folders
- **Every folder**: Gets a `_catalog/` (as dataset series for version history)

### Versioning & Immutability
- **Versioned IRIs**: Immutable content (the `v*` datasets)
- **Unversioned IRIs**: Mutable pointers that track current version
- **`_next` folders**: Work-in-progress staging area for collaborative editing
- **Version bumping**: On command, optionally on commit, cleans `_next` and normalizes filenames

### Content & Format Handling
- **HTML**: Always `index.html`, served by GitHub Pages for directory URLs
- **RDF formats**: Multiple distributions per version (`.trig`, `.jsonld`, etc.)
- **Machine discovery**: Catalog datasets specify available formats
- **Human vs Machine**: HTML for humans, RDF for machines, both versioned

## Aliasing System
- **Mechanism**: `schema:sameAs` relationships for IRI "renaming"
- **Backwards compatibility**: Old IRI returns only `schema:sameAs <new-iri>`
- **Lifecycle**: Can use `owl:deprecated true` for client-side redirects
- **Purpose**: Enables namespace refactoring without breaking existing references

## Semantic Foundation
- **Primary ontology**: Kosmion (relator-based foundational ontology)
- **Independence**: Semantic Flow works with any RDF data, not just Kosmion
- **Philosophy**: "Thing" over "entity" (following `schema:Thing` as most general)

## Technical Implementation
- **Platform**: GitHub Pages for free hosting and version control
- **SSG**: Lume (Deno-based) with custom plugins for RDF processing
- **Content negotiation**: Via catalog metadata (GitHub Pages has no custom headers)
- **Provenance**: Built into RDF data as metadata triples

## Current Status
- **Active development**: IRI scheme design finalized
- **Next steps**: SSG tooling implementation, workflow automation
- **Integration**: LLM-assisted import for ambiguous dataset situating

## Terminology
- **DSS**: Dataset Series (contains versioned datasets)
- **Thing**: General term for entities/concepts (not DSSs, namespaces, or catalogs)
- **Distribution**: Individual RDF files within a dataset version
- **Catalog**: DCAT-compatible metadata about related datasets/series

---

*This system creates a "dereferenceable semantic web" where every IRI provides an entry point into a knowledge graph with complete provenance and version history, using GitHub's infrastructure for reliability and GitHub Pages for free hosting.*