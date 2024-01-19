---
id: jhyu2uvqp5jxd0gs4t61ctk
title: Log
desc: ''
updated: 1705676709817
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

## t.2024.01.19.06

- I'm almost ashamed that this contrast has remained so murky for so long. There are two separate issues:
  1. for identifiers, are we identifying a web document or something that exists separately
  2. for web documents, are they about something else or are they their own thing
  
### #1 

- URL-like identifiers might return a document.
  - Is there an issue of "how would you refer to that document", in case you wanted to?
  - How does that document unambiguously convey that "the URL you requested is (primarily?) an identifier"

### #2

- is it just as easy as "everything is its own thing, but some web documents (like wiki pages) have essentially a single subject (likely specified as the title, but that could be specified in metadata by using an identifier), as well as one or more topics; and some things dont"
- Maybe the issue is "is a note a definition/model" of something, i.e. an "expression" in WEMI parlance. 

### Examples

- Does a daily journal note have a subject? Is its subject "Dave's January 19th"? Or is it "Some things Dave thought and did (or wrote) on January 19th"?
- 