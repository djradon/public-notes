---
id: c4wo7mdjzcit2bmvqr5sx4u
title: Namespace Repo
desc: ''
updated: 1730209708726
created: 1729878955236
---

- datasets across multiple repos can have IRIs detected for them, so the namespace repo is a 
  - top down "which datasets to download and scan for contained IRIs" 
  - which templates and template rules to apply
  - where the ssg and metalsmith-semantic-flow plugin operates from 
- can either be root (correspond to github username or org name, e.g. djradon.github.io) or 2nd-level (corresponding to an owned repo)
  - but we'll need an additional level for site assets, and "/ns" makes sense to indicate that the namespaces live below that

## Questions

- should repos be able to include HTML templates and entity-to-template mappings?
  - yes? but can be overridden at the namespace repo