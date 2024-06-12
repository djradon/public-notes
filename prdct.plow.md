---
id: kbohm7jjui6nz99gwfmulba
title: Plow
desc: 'package manager for ontologies, bringing established practices from software engineering into the world of ontology engineering. It similar to programming language package manager such as npm and cargo.'
updated: 1718210305820
created: 1718210044283
---

- https://plow.pm
- [[c.software.semantic]] [[c.registry.ontology]]
- 

## Description

_Plow_ consists of a few distinct core components:

-   the official registry (https://registry.field33.com/)
-   the website for the official registry
-   the Command Line Interface (CLI)

The official registry is a database of packages (called _fields_ in Plow) that is controlled via a JSON API. It allows anyone to publish packages for public or private consumption for any knowledge domain.

The [registry website (opens in a new tab)](https://registry.field33.com/) allows for discovery of packages via search, categories and keywords. It also provides an overview of relevant metadata (ontology project website, license, dependencies, etc.) for all versions of all packages.

The CLI allows for interacting with the registry from the terminal. It allows for e.g. publishing new fields, resolving dependencies of an ontology project and/or opening an ontology with dependencies in Protege.