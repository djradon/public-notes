---
id: c4wo7mdjzcit2bmvqr5sx4u
title: SFRootRepo
desc: ''
updated: 1730527221386
created: 1729878955236
---


- can either be "username/org pages repository"" (which automatically hosts content at the namesake url, so maybe call it a namesake repository, e.g. djradon.github.io) or 2nd-level (corresponding to an owned repo)
  - "/ns" makes sense for the 2nd-level repo name to indicate that namespaces live below that;
    - "/sf" is another option, to indicate it's a semantic flow site
- an SFRootRepo contains
  - the sflow ssg and configuration files
  - a 'docs' folder that contains the generated sf site
    - within 'docs' there's a folder for each namespace
    - an additional "root" level folder below "docs" for site assets named "_assets"
    - index.html and some index.* distribution for discovering what's contained in the site
  - a 'src' folder for repos (especially [[sflow.concepts.sf-data-repo]]), folders, and files which have NamedIndividuals and namespaces to generate the site for
  - templates and template mappings to apply to src items

  
## Questions

- should data-repos be able to include HTML templates and entity-to-template mappings?
  - yes? but can be overridden at the root/namespace repo