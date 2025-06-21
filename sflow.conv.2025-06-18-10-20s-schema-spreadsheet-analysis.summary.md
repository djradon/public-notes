---
id: x7ehbbdg9jx0odlhrar5wm0
title: '10-20s Schema Spreadsheet Analysis - Summary'
desc: ''
updated: 1750442476577
created: 1750441561198
tags: [user.claude.4.sonnet,prdct.claude.desktop]
---

# Semantic Flow Conversation Summary
**Date:** June 18, 2025  
**Context:** IRI Schema analysis and architecture refinement based on "10/20s schema" spreadsheet

## Key Architecture Decisions Made

### IRI Types (Finalized 7 categories)
1. **Namespaces** - organizational containers with namespace catalogs
2. **Things** - entities/concepts with thing catalogs  
3. **V-series** - versioning systems for datasets, catalog lives with dataset
4. **Datasets** - can be versioned or general, has unified catalog
5. **HTML pages** - index.html files for humans
6. **Distributions** - RDF files under versioned datasets
7. **Assets** - shared immutable resources in assets/ namespace

### URL Semantics (Confirmed)
- **Trailing slash (/)** = "refers" (abstract entities, series, concepts)
- **Filename** = "is" (concrete files, distributions, pages, assets)

### Source vs Output Architecture (Major Decision)
**Source Structure (Semantic Mesh):**
```
src/
├── assets/                   # immutable shared assets with explicit versioning
├── things/                   # mini-sites (presentation layer, no datasets)
│   └── people/dave-richardson/index.md
├── _data/                    # dataset repositories  
│   └── people-data/people-data.trig
└── templates/, config
```

**Generated Output:**
```
docs/
├── assets/                   # copied immutable assets
├── people/dave-richardson/   # thing with index.html + _catalog/
└── _data/people-data/        # dataset with v1/, v2/, _current/, _versions/, _catalog/
```

### Key Terminology Changes
- **"DSS" → "V-series"** - clearer about versioning role
- **"Entity" → "Thing"** - following schema:Thing as most general
- **"Dataset Series" → "V-series"** - versioning system that references dataset versions
- **"Semantic mesh"** - the source structure before weaving
- **"Weave"** - process that analyzes, versions, mints IRIs, generates catalogs

### Versioning and Immutability Model
- **All datasets are versioned** - even "current" is pointer to latest version
- **V-series**: DatasetSeries (DCAT v3) that tracks dataset versions
- **On weave**: analyze changes, mint new IRIs, bump versions, generate catalogs
- **Immutable assets**: explicit versioning in filenames (headshot-2024.jpg)
- **sflow:immutable property**: distinguishes v*/ (true) from _current/ (false)

### Catalog Simplification
- **No separate catalog files in source** - all auto-generated
- **Unified catalogs**: dataset + v-series metadata live together
- **Thing catalogs**: discovery metadata about related datasets
- **Namespace catalogs**: directory of contained things and datasets
- **No _next folders**: catalogs are machine-generated only

### Data vs Presentation Separation  
- **Things = mini-sites**: presentation layer with templates, no datasets
- **_data = repositories**: actual RDF content with versioning
- **Clear semantic distinction**: thing IRIs refer to entities, not their data
- **Entity catalogs**: link to relevant datasets via discovery metadata

### Asset Management
- **Shared assets/ namespace**: prevents duplication across versions
- **Immutable once published**: use new filenames for changes
- **Absolute paths**: /assets/images/... for portability
- **HTML history support**: old HTML can still access original assets

### Aliasing vs Renaming
- **True aliasing**: schema:sameAs for multiple names (things, v-series only)
- **Renaming**: owl:deprecated + rdfs:seeAlso for structural changes
- **No aliasing for**: namespaces (too complex), datasets (immutable)
- **Client-side redirects**: SSG can generate based on owl:deprecated

### File Naming Rules
- **Dataset files must match folder names**: people-data.trig in people-data/
- **Case sensitivity preserved**: file capitalization must match folder
- **Import validation**: external data renamed to match target structure

## Unresolved Issues

### V-series IRI Ambiguity
**Problem**: Same IRI represents both abstract v-series and concrete datasets
- `_data/people-data/` = dataset IRI (general/current)  
- `_data/people-data/_versions/` = v-series IRI (versioning metadata)
- `_data/people-data/v3/` = specific dataset version

**Decision**: _versions/ functions as named thing with no content, unified catalog under dataset IRI

### Complex Dataset Hierarchies
**Datasets of datasets**: Need clear patterns for hierarchical data structures
- Master dataset references chunks
- Each chunk has own v-series
- Version bumping cascades (if chunk changes, parent must bump)

### API Architecture (Proposed)
- **API-first design**: self-contained service with RDF store backend
- **CLI as thin wrapper**: Cliffy calls HTTP API
- **Local/remote flexibility**: same service works standalone or networked  
- **Filesystem monitoring**: enables incremental weaving for large meshes

## Implementation Priorities

1. **Define sflow ontology**: properties like sflow:immutable for distributions
2. **Build weave engine**: analyze changes, mint IRIs, version datasets  
3. **Template system**: flexible rendering for things (Markdown, JSX, Vento)
4. **Import tooling**: namespace-aware external data integration
5. **API service**: persistent state with RDF store backend

## Context for Future Development

**Core Philosophy**: Stable identifiers pointing to versioned data creates comprehensive dereferenceable semantic web with full historical context.

**Two Hearts of Semantic Flow**:
1. **Stable Identifiers**: permanent IRIs for discovery
2. **Versioned Datasets**: immutable data with complete provenance

**V-series Definition**: Every dataset has associated DatasetSeries (DCAT v3) that tracks versions. On weave, any dataset with changed data gets new version.

**Publishing Workflow**: Edit semantic mesh → Weave (version/catalog) → Build site → Deploy docs/ to GitHub Pages