---
id: zsaw29dxuikv8rbgofvjm78
title: Metalsmith Semantic Flow
desc: ''
updated: 1730209408306
created: 1730208164226
---

## metalsmith-semantic-flow

Metalsmith-Semantic-Flow could be a custom plugin or an adaptation of Metalsmith tailored to handle RDF data for the Semantic Flow project. It would automate the generation of HTML pages and dataset distributions for each NamedIndividual in the namespace, all while ensuring that each dataset follows your specific conventions. Here’s a concept outline:

1. **Data Parsing and Structuring**:
   - Parse RDF files (TTL, JSON-LD) within the project and map each NamedIndividual to an IRI.
   - Use the `_default` and `_catalog` structures for versioning, generating `_default/v1` datasets as the main data source and `_catalog/v1` for catalog metadata.

2. **Dynamic Metadata Injection**:
   - Define a base template for NamedIndividuals, dynamically injecting metadata like `relator-genesis`, `relator-tombstone`, and contextual properties.
   - Auto-generate index pages (`index.ttl`, `index.html`) with `owl:imports` for linked datasets and catalogs.

3. **Namespace Handling**:
   - Host the actual namespace at a lower directory level to allow for multiple namespaces, with individual NamedIndividual pages linked at `/ns/namespace-name/`.
   - Automatically track updates in the `contributing-repos` directory, ensuring only new or modified data triggers re-rendering.

4. **Template Customization**:
   - Support for customizable templates per NamedIndividual type, allowing you to apply different layouts based on categories of individuals (e.g., specific templates for `Person` or `Location`).

5. **Versioning Workflow**:
   - Implement your `_default` dataset workflow, with commit hooks or git triggers to copy new data to versioned datasets.
   - Mirror changes across versioned IRIs, using `_history` or similar paths as needed for separation between regular and historical IRIs.

6. **Catalog and Dataset Series Integration**:
   - Integrate `dcat:Catalog` and dataset series, with a subclass like `ko:CatalogSeries` to maintain dataset continuity.
   - Generate catalog IRIs like `catalog/dave-richardson-catalog.ttl` and `catalog/history/v1/`, adding version metadata using PAV if DCAT alone doesn't suffice.

Let me know if this is on target for your Semantic Flow setup, or if you want specifics on particular plugins or handling certain data.

## contributing-repos => src

### dave

instead of "contributing-repos", let's just use "src"... it's possible people will want to generate only from a single file, or a collection of files that aren't in repos, etc.

### chatgpt

Got it. Using "src" will make it flexible for single files or collections that aren’t repos. This should make it easier to scan for updates or new data without needing a repository structure.

## no "history" or "_history"

### dave

We dropped using history or _history as part of the IRI. The version identifier indicates history, and now I'm thinking to use "current" everywhere to refer to the current dataset, and people can modify a corresponding distribution, and the modifications will get copied to a new version on commit. It'll be tricky if two different distributions are modified, but I can at least imagine software that merges two modified distributions before allowing a commit.

### chatgpt

Got it. Using "current" as the identifier for active datasets will streamline things, especially with a merge feature for concurrent distribution modifications. This setup should make it easier to track and update without extra history paths.

## 