---
id: 3gVpHwZTquGdBieRLcxNR
title: Conventional Commits
desc: ''
updated: 1672637616382
created: 1633088347659
---

## #summary

- Commits MUST be prefixed with a type, which consists of a noun
  - e.g feat:, fix:, build:, chore:, ci:, docs:, style:, refactor:, perf:, test:
- scope after type is optional
- ! for breaking change

- [[p.hasURL]] https://www.conventionalcommits.org 
- [[p.isRelated]] https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716
- [[p.hasSpecification]] https://www.conventionalcommits.org/en/v1.0.0/

## Thoughts

- `!` used for BREAKING CHANGE
  - `!` could be used in [[gd]] for emphasizing tags, predicates, or objects  ^cN92w9TjfnXM
    - hard to imagine the need to emphasize an subject but I suppose 
      - (since subjects are ultimately equivalent to objects related with an inverse predicate)
    - emphasis could denote "default" or preferred properties
- always at the start, understandably... 
  - but
    - if you treated them as tags, you could include them at the end, or anywhere internal
