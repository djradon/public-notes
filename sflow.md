---
id: ggw3ek46ptgebsgxgihr1dh
title: Semantic Flow
desc: ontology, tooling, and workflow for publishing semantic data
updated: 1750485436506
created: 1716959415785
---

- requirements: [[sflow.requirements]]
- issues: [[sflow.issues]]

**dereferenceable, versioned semantic mesh** will be the foundation for a new era of knowledge graphs.

# Semantic Flow & IRI Schema Context Summary

## Project Overview
**Semantic Flow (sflow)** is an ambitious system for publishing semantic data with complete version history using GitHub infrastructure. It aims to solve the problem of evolving graph data by providing immutable versioning while maintaining dereferenceable IRIs.

**Dereferenceable:** Every IRI in the system can be accessed via HTTP and returns meaningful content - either human-readable HTML pages or machine-readable RDF data. This creates a web where any resource can be explored and discovered.

## Two Hearts of Semantic Flow

**1. Stable Identifiers:** Permanent IRIs that refer to things (people, concepts, namespaces) and provide discovery points into the knowledge graph. These identifiers never change meaning, though the data describing them evolves.

**2. Versioned Datasets:** All data is stored in immutable versioned datasets. When data changes, a new version is created while preserving complete history. This provides auditable provenance and enables time-travel queries.

**V-series:** Every dataset has an associated DatasetSeries (as defined in DCAT v3) that tracks each version of the data. On weave, any dataset that contains changed data gets a new version. The v-series manages this versioning lifecycle and provides metadata about the dataset's evolution over time.

**Key Innovation:** The combination of stable identifiers pointing to versioned data creates a comprehensive semantic web where any resource can be explored with full historical context.

## Namespace Architecture



### Three-Way Recursive Namespace Division
Every folder at any level is one of three types:

1. **Sub-namespace** - contains other folders following the same pattern
2. **Thing reference** - terminal folder with `index.html` and `_catalog/`
3. **`_series/`** - contains dataset series with `_v*` versioning subfolders

## Source vs Output Architecture

**Source:** A semantic mesh - a directory structure that corresponds to namespaces, thing identifiers, and datasets; plus assets, templates, configuration, and metadata.
```
src/
├── assets/                   # immutable shared assets
│   ├── images/
│   │   ├── dave-headshot-2024.jpg
│   │   └── company-logo.svg
│   ├── styles/
│   │   └── theme-2024.css
│   └── templates/
│       ├── person.html
│       └── dataset.html
├── things/                   # mini-sites (presentation layer)
│   ├── people/
│   │   └── dave-richardson/
│   │       ├── index.md      # or .jsx, .vento
│   │       └── custom.css
│   └── concepts/
│       └── friendship/
│           └── index.md
├── _series/                  # data repositories
│   ├── people-data/
│   │   ├── people-data.trig  # MUST match folder name
│   │   └── people-data.meta.yml  # DSS metadata
│   └── big-dataset/          # DSS of DSSs
│       ├── big-dataset.trig  # master dataset
│       ├── big-dataset.meta.yml
│       ├── chunk-a/
│       │   ├── chunk-a.trig
│       │   └── chunk-a.meta.yml
│       └── chunk-b/
│           ├── chunk-b.trig
│           └── chunk-b.meta.yml
└── import-config.yml         # namespace-aware import settings
```

### Generated Output Structure (Publication)
```
docs/
├── assets/                   # copied from src/assets/
├── people/                   # sub-namespace
│   ├── index.html           # namespace description
│   ├── _catalog/            # namespace catalog DSS
│   │   ├── _v1/, _v2/, _current/ (each with index.html)
│   └── dave-richardson/     # thing reference
│       ├── index.html       # generated from src template
│       ├── index_v1.html, index_v2.html  # HTML history
│       └── _catalog/        # thing catalog DSS
│           ├── _v1/, _v2/, _current/ (each with index.html)
└── _data/                   # dataset container
    └── people-data/         # dataset IRI
        ├── index.html       # dataset description
        ├── _v1/, _v2/, _current/  # dataset versions (each with index.html)
        ├── _v-series/       # v-series IRI (references dataset versions)
        │   └── index.html   # describes versioning system
        └── _catalog/        # unified catalog DSS (dataset + v-series metadata)
            ├── _v1/, _v2/, _current/ (each with index.html)
```

## Key Constraints & Rules

### Source Organization
- **Things**: Mini-sites with templates, no versioning, no datasets
- **DSSs**: Data files must match folder names (`people-data.trig` in `people-data/`)
- **Assets**: Immutable once published (explicit versioning in filenames)
- **Metadata**: Separate `.meta.yml` files for DSS descriptions
- **Templates**: Flexible (Markdown, JSX, Vento, etc.)

### Output Organization
- **Thing folders**: Only `index.html`, `index_v*.html`, and `_catalog/`
- **Series folders**: Only `v*`, `_current`, `_catalog/`
- **RDF files**: Only exist in `v*` and `_current` version folders
- **Every namespace and thing**: Gets a `_catalog/` DSS (namespace catalog or thing catalog respectively)
- **Every DSS**: Gets a `_catalog/` DSS (series catalog) for series-level metadata

### File Naming Rules
- **Case sensitivity**: Preserved - file capitalization must match folder
- **Consistency**: Dataset files must match containing folder name
- **Import validation**: External data must be renamed to match target structure
- **Asset versioning**: Explicit versioning in filenames (e.g., `headshot-2024.jpg`)

### Content & Format Handling
- **HTML**: Generated from templates, served by GitHub Pages
- **RDF formats**: Multiple distributions per version (`.trig`, `.jsonld`, etc.)
- **Assets**: Absolute paths (`/assets/images/...`) for portability
- **Machine discovery**: Catalog datasets specify available formats and series info
- **Things vs Data**: Clear separation - things are presentation, DSSs are data

## Versioning & Immutability
- **Source simplicity**: No versioning in source - just current content
- **Output versioning**: SSG creates `v*` versions when content changes
- **Immutable assets**: Once published, assets never change (use new filenames)
- **Rollback capability**: Git commits after successful generation
- **Permanence checking**: Validates no historical IRIs lost, no immutable data changed

### Catalog Content & Purpose
- **Namespace catalogs**: Directory of contained things and datasets within the namespace
- **Thing catalogs**: Discovery metadata - what dataset series reference this thing, basic identification
- **Dataset catalogs**: Unified metadata covering both dataset content AND v-series versioning information
- **Individual distributions**: Metadata lives within the dataset version itself, not in separate catalogs

## Import & External Data
- **Namespace-aware**: Import process assigns local IRIs within appropriate namespaces
- **File naming**: External data renamed to match target folder structure
- **Ontology import**: External ontologies get local IRIs with `schema:sameAs` to external IRIs
- **Validation**: Import process validates filename matches target location

## Aliasing vs Renaming
**True aliasing**:
- **Purpose**: Multiple names for the same resource
- **Implementation**: `schema:sameAs` relationships in alias distributions
- **Allowed for**: Things and DSSs
- **Not allowed for**: Namespaces (too complex), datasets (immutable)

**Renaming/moving**:
- **Purpose**: Change canonical location/name  
- **Implementation**: `owl:deprecated` + `rdfs:seeAlso` or `dcterms:replaces`
- **Namespace moves**: Expensive operation copying all content, optional redirect preservation

## Publishing Workflow
1. Edit content in `src/` (things, datasets, assets)
2. Commit source changes to Git
3. Run SSG build process
4. SSG compares source with last published versions
5. Create new `v*` versions in `docs/` for changed datasets
6. Generate updated `_current/` folders and `index.html` files
7. Auto-generate all `_catalog/` metadata from source data and templates
8. Copy immutable assets to `docs/assets/`
9. Commit generated output to Git (rollback capability)
10. Deploy `docs/` folder to GitHub Pages

## Technical Implementation
- **Platform**: GitHub Pages serving from `docs/` folder
- **SSG**: Lume (Deno-based) with custom plugins for RDF processing  
- **Source vs Output**: Clean separation - source for authoring, output for publication
- **Data Sources**: Contained in repo (`src/` folder) or external retrieval via import tools
- **Content negotiation**: Via catalog metadata (GitHub Pages has no custom headers)
- **Provenance**: Built into RDF data as metadata triples
- **Asset management**: Immutable `assets/` namespace prevents breaking HTML history
- **Permanence checking**: Validates no historical IRIs lost, no immutable data changed

## Semantic Foundation
- **Primary ontology**: sflow (semantic flow ontology for dataset series and versioning)
- **Compatibility**: Works with any RDF ontology (Kosmion, schema.org, FOAF, etc.)
- **Philosophy**: "Thing" over "entity" (following `schema:Thing` as most general)

## Current Status
- **Active development**: Architecture design finalized
- **Next steps**: SSG tooling implementation, template system, import tools
- **Integration**: LLM-assisted import for ambiguous dataset situating

## Terminology
- **V-series**: Versioning system for a dataset (references dataset versions, 1:1 relationship)
- **Thing**: General term for entities/concepts (mini-sites, not datasets)
- **Distribution**: Individual RDF files within a dataset version
- **Catalog**: DCAT-compatible discovery metadata, unified for datasets and their v-series
- **Assets**: Shared immutable resources (images, CSS, JS) in `assets/` namespace
- **Import**: Process of bringing external data into namespace-aware source structure

---

## Features

- RDF dataset-series oriented for semantic versioning and provenance
- every named entity can have a catalog series, which describes facilitates discovery by describing entity-related resources (including the default dataset series)
- use github or gitlab to manage namespaces using [[sflow.concepts.sf-root-repo]] and mint IRIs
- an [[sflow.concepts.sf-data-repo]] could have files/distributions for more than one namespace, so it should have each of those namespaces segregated by a top-level folder



## Related Prodcuts / Possible Components

- [[prdct.comunica.query-sparql-file]]

