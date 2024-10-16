---
id: qam1t76y0kjtzwjl47fpc5s
title: Best Ontology Development Environment Tool? 
desc: ''
updated: 1729105824009
created: 1729105165809
---

- https://www.reddit.com/r/semanticweb/comments/1fqec66/best_ontology_development_environment_tool/
- mentions: [[prdct.atomicserver]]
- posted: 2024-09-26
- creator: @daniel-bakas


## Discussion

### Protege limitations according to @speckledlemon:

-   The visualization and most of the UI is intuitive for me as someone who prefers CLIs, but there are no ways to visualize the ontology graph (doesn't bother me much) and the distinction between what options are available in the main menus versus context menus is unclear (bothers me a lot). The UI for saving to different formats is annoying.
    
-   No SHACL support.
    
-   Integration with reasoners seems good, though I've only used Hermit. I like the UI for inference explanations.
    
-   My main problem is that it is decently buggy (views don't update without manually clicking) and, when the reasoner is active, painfully slow. Some of it may be due to a poorly-constructed ontology, but it's noticeable even with the pizza example just clicking between the different classes. Imports of ontologies from other local files doesn't happen automatically even though Protege knows about them in the catalog. I'm sure there are other things.

If there was another option that cost money but would tell me up front how much a personal license cost, I'd probably go for that. For "high-impact big scale" projects I would definitely not be using Protege.

