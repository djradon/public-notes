---
id: fd1whkyvoagggk6ubysjl50
title: Semantic Flow Log
desc: ''
updated: 1730210072947
created: 1727801720160
---

## t.2024.10.01.09

### chatgpt memory

- dave: Remember: I'm trying to develop a static-site generator called "Semantic Flow" that takes ontologies defined in RDF and/or conforming RDF data files and generates a static site to be hosted on GitHub pages that includes HTML-based index files (that can be based on a template or customized as necessary) that describe identified resources and link to raw RDF data files (possibly in multiple formats) that can be access by semantically-aware applications.

## t.2024.10.28.15

- tried metalsmith-ldschema, underscored the point that the docs folder/site might need some javascript and templates and assets that could interfere with the namespace, so the actual namespace will probably need to live the next level down
- got a site to build... it's basically empty because metalsmith-ldschema only generates pages for classes and properties, but still, feeling good.

## t.2024.10.29.06

- I've been wanting to have a place where people can just make changes directly to the RDF, and the tooling (on commit) copies it to a new version. "current"
- I think there's a decision to be made between using the src hierarchy structure and generating the hierarchy; it might be related to the tension between supporting multiple repos. 
  - probably doesn't make any sense to call it a namespace-repo any more... the namespaces live under it