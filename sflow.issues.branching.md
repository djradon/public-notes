---
id: tqy6rmegip3t0jqpku9qbh5
title: Branching
desc: ''
updated: 1750294114964
created: 1750294102286
---

Git branches are great for development workflow but break IRI semantics because the IRIs embedded in your RDF data become contextually invalid.

**The problem:** If you have `<https://djradon.github.io/ns/dave-richardson/>` in your RDF, but you're on branch `feature/new-schema`, that IRI doesn't actually resolve to the branch content.

**Potential approaches:**

1. **Development-only branching** (.8) - Git branches are just for collaboration, always merge to main before publishing. Simple but limits experimentation.

2. **IRI rewriting during build** (.6) - Detect branch context and rewrite IRIs to include branch info (`/ns/dave-richardson/branch/feature-new-schema/`). Complex and breaks semantic consistency.

3. **Branch-aware resolution** (.7) - Keep IRIs stable but make your SSG workflow generate branch-specific endpoints that redirect appropriately. Maintains semantics but adds infrastructure complexity.

4. **Separate development domains** (.5) - Use different domains for branches (`dev.djradon.github.io` vs `djradon.github.io`). Clean separation but requires more setup.

The cleanest might be treating Git branches as pure development tooling - you get the collaboration benefits without breaking RDF semantics (.8). Your semantic-flow native branching would handle actual data versioning while Git handles code evolution.

What's driving the desire for Git branching integration? Collaborative editing scenarios?