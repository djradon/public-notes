---
id: rqvxekptxti2amhyjjm36hi
title: LDengine
desc: 'Engine to power your Linked Data apps and pipelines '
updated: 1754021763774
created: 1754021723915
---

- https://github.com/ldengine/lde

Features

    Discover and retrieve datasets from DCAT-AP 3.0 registries.
    Query and transform datasets with pure SPARQL queries (instead of code or a DSL): no vendor lock-in.
    Use SPARQL endpoints directly when possible; import data dumps to a local endpoint when necessary.
    Compose pipelines with YAML (for non-technical users) or TypeScript code (for developers).
    Get started quickly with ready-to-use Docker images.

Packages

LDE is an Nx monorepo that includes the following packages:

    @lde/dataset: core objects dataset and distribution
    @lde/dataset-analyzer-pipeline: statistical analysis of datasets
    @lde/dataset-registry-client: retrieve dataset descriptions from DCAT-AP 3.0 registries
    @lde/distribution-download: download distributions for processing locally
    @lde/local-sparql-endpoint: quickly start a local SPARQL endpoint for testing and development
    @lde/pipeline: build pipelines that query, transform and enrich Linked Data
    @lde/shacl-docgen: generate documentation from SHACL shapes
    @lde/sparql-importer: import data dumps to a local SPARQL endpoint for querying
    @lde/sparql-qlever: QLever SPARQL adapter for importing and serving data
    @lde/task-runner: task runner core classes and interfaces
    @lde/task-runner-docker: run tasks in Docker containers
    @lde/task-runner-native: run tasks natively on the host system
    @lde/validator: validate datasets and pipeline outputs against SHACL shapes
    @lde/wait-for-sparql: wait for a SPARQL endpoint to become available
