---
id: YLmAMnIoOcUUOlbXQGNFl
title: Dendron
desc: ''
updated: 1638032539880
created: 1631142984146
---


## [[hasConcepts]]

### References 

embed content from other notes

- [aka] transclusions
- [[p.hasURL]] https://wiki.dendron.so/notes/f1af56bb-db27-47ae-8406-61a98de6c78c.html

### Block Anchors

- [[p.differentFrom]] header references

### Snippets

- just uses vscode's snippets functionality
- comes with a basic set: todo, date, and time 
- annoyance: doesn't de-dupe so three-vault workspaces get three sets of snippet suggestions
  - [ ] remove duplicate

### aliasMode

- what to do when pasting a link
- selection only applies when text is selected, but that's the mode for me.
  - seems like it should be orthogonal to other [aliasMode](https://wiki.dendron.so/notes/eea2b078-1acc-4071-a14e-18299fc28f47.html#aliasmode) options 


## Feature ideas

- allow setting aliasMode per note
- note links can use aliases, so instead of seeing [\[solution.dendron]] I can just see [\[Dendron]] or maybe even Dendron^ in my editor
- [ ] flexible capitalization settings
  - I don't want predicate notes to be capitalized
- inclusion macros:
  - all blocks
    - match "tags" or links
  - all notes
    - match tags, links, hierarchy (does this exist already? it does for sub-notes)
- ![[Multi Repo Auto save Commit Push|pi.multi-repo-auto-save-commit-push]]
- pretty-ref setting per reference 
  - usePrettyRefs is impossible course
  - would be nice to have a single-line prettyref 
- use "title" instead of hierarchy (this already happens on same page, see altLabel)
- editor background changes based on vault
- wikilink color changes based on vault or type  ^SUKl67TO9Ch6
  - for the colorblind we could do something like background, outline, style, and font changes based on vault, or links have boxes (sharp corner, rounded corner, etc)
- `semantic links` this is basically what predicates enable
- ![[pi.RRI#^JZbCUAYF0h0h:#*]]
- ![[gd#^YzwILFSI4oSJ]]
- make @ references configurable (as to hierarchy)
- make transclusion of frontmatter or other properties, see https://foambubble.github.io/foam/proposals/inclusion-of-notes#include-an-attribute-of-a-file-note-property-or-frontmatter
- 

## interesting github issues

## unreported issues
- move to capitalized version doesn't work
- refactor hierarchy in the middle somewhere is wonky
- dendron move doesn't fix same-note wikilinks 
- when moving a note between vaults, referenced files should be moved to? or at least copied? or prompt-to-copy after checking whether any other references exist?
- preview capitalizes lvl-4 headings
- does "move note" always fail the first time?
- too much newlines added to .gitignore ^hETGc7F9cXEZ
- sometime can't choose "references" vault for new note creation
  - "distroid-issue-13-digital-gardens" allows
  - "article.distroid-issue-13-digital-gardens" doesn't
  - 2021-09-25 this actually seems to be a consistent mis-labelling of one of the options -- two options can get repeated and you can usualy figure out which one is mislabelled

## vocabulary

- `books.` is hierarchy
- `books.tags` is a namespace

## tips and tricks

- every hierarchy unique across vaults. 
  - otherwise,
    - too many misfilings
- [roll to-do items forward in Dendron](https://wiki.dendron.so/notes/61055b5f-6216-4fd3-b9a1-82f79017b59e.html) with hooks
  - uses https://github.com/kalyan02/dendronutils 
- [set keyboard shortcuts for selectionExtract](https://wiki.dendron.so/notes/ad270a7d-2aed-4273-8319-eb6536e38b29.html)
- [[p.hasIssue]] wanna clean up a note, but preserve the old junk for  reference?  ^QtQux3rkT2Hc
  - [[p.hasPossibleSolution]] move it to ".archive"
    - doesn't matter if it's sloppy, but you can keep the archive organized by mimicing headers from main note
    - might call it discussion instead of archive, a la wikipedia

### beware the bare file

- [[p.hasPrinciple]]
  - "every note in a namespace" (maybe with a few exceptions like "now")
- for a long time I was tempted to just start dumping stuff in the root, i.e., no hierarchy
  - after all, it reads better not to have to see the namespace
  - not to mention, vaults imply a hierarchy
- but these days, everything should be in a type-consistent hierarchy, otherwise
  - refactoring is a pain
  - autocomplete is less powerfull
  - 

## [[p.hasRelatedResource]]

- [[t.km.dendron]]

### [[p.hasCaseStudy]]

- [P.A.R.A. with Dendron](https://wiki.dendron.so/notes/664c7980-f605-43ad-a931-c139740777c8/)
  - [[p.isRelated]] [[t.km.PARA]]
  - [[p.hasCitation]] https://fortelabs.co/blog/para/
- 

