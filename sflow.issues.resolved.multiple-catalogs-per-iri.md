---
id: mjjgm10blsfa2yoh9ps1m8i
title: Multiple Catalogs per IRI
desc: ''
updated: 1750368427619
created: 1750295032498
---

If we just use _catalog to point to the current dataset, we don't need _default anywhere. 

## Conversation

I'm thinking to get rid of catalog/default, unless we need multiple catalogs per IRI.

### @claude.4.sonnet

**On catalog history tracking** (.8) - Yes, catalogs should probably hold the complete `_default` pointer history. This gives you:
- Temporal queries ("what was Dave's default dataset in March?")
- Audit trails for data governance
- Rollback capabilities

**On `catalog/_default`** (.7) - You're right to question this. If each entity gets one primary catalog, `_default` becomes redundant indirection. Just use versioned catalogs: `/catalog/v1`, `/catalog/v2`, etc.

**The infinite loop concern** (.6) - `_default/_default` would indeed be problematic. Your instinct is right - keep pointer history in the catalog metadata, not in nested pointer structures.

**One clarification question:** When you say "Things referenced in datasets will get their own IRIs carved out" - does this mean auto-generating entity IRIs for every subject/object mentioned in the RDF? That could create a lot of entities quickly (.7).

The quasi-immutability model is pragmatic - acknowledging that sometimes you need escape hatches while maintaining the general principle of preservability.