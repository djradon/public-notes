---
id: jhyu2uvqp5jxd0gs4t61ctk
title: Log
desc: ''
updated: 1702213558670
created: 1702213558670
---

## t.2023.12.10.05

removed:
```
- when regular links (raw URL, URL in angle brackets, or URL in parentheses after single-square link text, aka markdown-style links) for subjects, predicates, and objects, they are always resourceRefs
- wikilinks to notes in the local workspace (LRIs?) or URIs [[https://www.markdownguide.org/basic-syntax/]] are always used as subjectIndicatorRef
  - so you can't say anything about notes themselves?
    - maybe you put it in the frontmatter
    - maybe you create a second, special "ar" note.
    - maybe a special syntax to treat local
      - maybe <http:///vs.rdfs-vs-owl.md>
- if you want to say something about something that's not addressable
  - create a note for it
  - but I wanna use  an "indicator note" that someone else has made? Or I made and published on the web somewhere, and it's not in my local workspace
    - make a new local note, point it at the indicator note. 
- `prdct.toml` is kinda an identifier; unlike a corresponding note in the topic hierarchy, it won't change
- differentiate resources that are addressable with `hasURL` - but not sure if that helps
```
