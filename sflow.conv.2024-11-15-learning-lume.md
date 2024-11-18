---
id: 151gd9o6fdhivpph5brkrdr
title: 2024 11 15 Learning Lume
desc: ''
updated: 1731667557127
created: 1731667483101
---

- topics: [[prdct.lume]] [[prdct.deno]]

## _data doesn't get site passed, but plugins do (dave)

I think the right way to get the site passed for dynamic creation is with lume modules. "Plugins can't do anything that you couldn't do in the _config.ts file, but they provide a better interface to organize and reuse your code." There's an example of a nav module here: https://github.com/ansanloms/lume-theme-docs/blob/main/examples/_config.ts 

It mentions "for (const page of pages) {"

## _data doesn't get site passed, but plugins do (dave)

