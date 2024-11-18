---
id: h7qdzwumq4unjwwawv6l3rt
title: TypeScript Vs JavaScript
desc: ''
updated: 1731596210726
created: 1713214985724
---

## Opinions

### You can do literally everything TS can with JSDocs

 By adding // @ts-check to the top of a .js file, it turns on the TS engine, which can infer types from JSDocs in the same way it does from TS. You can do literally everything TS can with JSDocs. I would strongly recommend the eslint-plugin-jsdoc. I use this ruleset:

    https://github.com/tjw-lint/eslint-config-tjw-jsdoc


### Use d.ts 

- https://www.reddit.com/r/vuejs/comments/st2zkt/comment/hx17byc/
  - " currently do both:

    .d.ts for types

    js files with docblocks that use those types"

## References

- https://www.reddit.com/r/vuejs/comments/st2zkt/jsdoc_or_typescript/
- https://javascript.plainenglish.io/why-some-major-projects-are-ditching-typescript-219582449e17