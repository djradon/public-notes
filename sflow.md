---
id: ggw3ek46ptgebsgxgihr1dh
title: Semantic Flow
desc: a workflow and tooling for publishing semantic data
updated: 1729874586868
created: 1716959415785
---

## Requirements

- for "dereference" pages you don't want all assertions, only some of the most useful ones, perhaps with links to where you can get more
- mapping of templates to facets, namespaces, datasets


## Dynamic Client-Side

- the HTML (mostly index.html) for each entity/graph/dataset/catalog might access a text-based data source that specifies which template to use, which data to incorporate (via catalog processing), and then write the response dynamically. 
  - maybe the data source is the default graph for the entity, or a special dereference-page graph
- Users could also customize their views and save those setting in a cookie, that would be integrated into the page

## References

- [[ar.base-platform-for-knowledge-graphs-with-free-software]]
- https://www.rockyourcode.com/how-to-deploy-eleventy-to-github-pages-with-github-actions/