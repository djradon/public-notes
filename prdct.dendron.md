---
id: YLmAMnIoOcUUOlbXQGNFl
title: Dendron
desc: ''
updated: 1729193263416
created: 1631142984146
similar: "[[prdct.foam]]"
---

- creator: @kevin-lin
- [[c.software.Knowledge-Base]] 

## Tips

- don't end your dendron top-level domain with the same letter. i.e., `prdct.`, `t.` - it hampers search autocomplete ^ln5q1ooyf17z

## Publishing

- `rm -rf .next && rm -rf docs`
- `dendron publish export --target github --yes`
- to customize the next.js template... use "--dest       override where nextjs-template is located"
  - https://docs.dendron.so/notes/PgwAXFfotfgpFVqHQRlBl/
- customizing the header is also apparently an option
- for "files to include", vaults have to be specified as, e.g. ./public-notes
  

## Resources

- [Deploy to Github Pages using Actions with both Private and Public Vaults](https://wiki.dendron.so/notes/N2XTqKPFEkKCFJ6kRnzl0/) mostly worked, but couldn't get permissions to commit