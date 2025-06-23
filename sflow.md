---
id: ggw3ek46ptgebsgxgihr1dh
title: Semantic Flow
desc: ontology, tooling, and workflow for publishing semantic data
updated: 1750657617661
created: 1716959415785
---

- requirements: [[sflow.requirements]]
- issues: [[sflow.issues]]

A **dereferenceable, versioned semantic mesh** will be the foundation for a new era of knowledge graphs.

**Semantic Flow** is a framework for managing and publishing knowledge graphs and other semantic data by leveraging GitHub, Gitlab, and other free static hosting services. It enables a **dereferenceable Semantic Web** where every HTTP IRI returns meaningful content.

## Features

- own your own data
- complete version history when you want it
- reliable persistence
- seamlessly integrate other data sources anywhere in your mesh

## Elements

[[Semantic meshes|sflow.concepts.mesh]] provide data management  and [[semantic sites|sflow.concepts.site]] solve data publishing with four types of weavable elements:

- **Datasets**: bundles of data, with optional immutable, checkpointed history
- **Namespaces**: organize your data in familiar URL-based hierarchies
- **Identifiers**: Persistent URLs which refer to namespaces, datasets, and other things (like people, concepts, whatever). Good identifiers are useful for public data in general, and essential the Semantic Web
- **Asset Bundles**: every identifier-folder can contain two file trees:
    - **Web Assets (the _assets folder)**: URL-addressable pictures, templates, audio, etc.
    - **Excluded Assets (the _x folder)**: things that don't go on the web, but which help 

Files and folders that are present in aren't consistent with these elements are ignored in the weaving process, 


## Workflow

### Creation

- Semantic-flow is designed to work with git, and a good place to get started is with a new, empty git repository
- create one or more folders. In general, folders are considered identifier folders if they contain a subfolder named _id.
    - folders that do not contain an _id folder will be ignored.
- the "docs" folder name has a special meaning in some Github publishing workflows, so should be avoided as a identifier name in general. ^pnoqpr3ff4za


### Editing

- add new identifiers, namespaces, datasets or [[sflow.concepts.asset-bundle]], or modify existing ones

### Weaving
- creates support system files as needed
- checks mesh consistency and reports issues
- "bumps" versions of [[versioned datasets|sflow.concepts.dataset.versioned]]
- you can weave a part of your semantic mesh, or the whole thing

### Publishing

**SSG Workflow**: Lume-based with plugins for RDF processing, automatic provenance generation, and version management.

**Aliasing**: Uses schema:sameAs for IRI renaming while maintaining backwards compatibility.

**Content**: Only v* folders contain RDF files (index.trig, index.jsonld, etc.). Everything else gets index.html for GitHub Pages compatibility.


## Key Constraints & Rules

### Semantic Mesh Organization
- **Things**: Refer to any entity you might need to talk about, real or conceptual, but function as mini-sites with their own catalog and assets templates, no versioning, no datasets
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

