---
id: h6tift75ff3f6yfw9032moh
title: Destructuring
desc: 'a convenient way to extract values from arrays or properties from objects and assign them to variables. This allows you to pull out multiple fields from an object or elements from an array in a concise and readable manner'
updated: 1732962820773
created: 1732962599067
---

## Examples

### Weave

```typescript
const { include = [], exclude = [], excludeByDefault = false, branch: providedBranch } = inclusion.options || {};
```