---
id: ztv3vka10n6y3optp1fwlad
title: Hedgedoc
desc: ''
updated: 1721758123376
created: 1721757063515
---

- https://hedgedoc.org/

## Issues

### No Git Support in HedgeDoc

- "Let's say we have a sentence "The sky is blue" and now, 2 people work on this document. A adds "Today" at the beginning, and the other adds "like the sea" at the end.

How are we supposed to represent this in git? Making a commit for each of them? That would result in hundreds of commits within a few minutes for 2 or 3 people working on a document, and none of them would make sense. Also what to put there as a commit message?

Or should we record the changes of each user for 5 minutes and then make a commit? That doesn't work. Git would break in a merge conflict here, which is not properly resolvable. Well, might by using some force towards the final document we already recorded in CodiMD? Maybe, but I foresee a lot of trouble.

So far, I consider real-time collaboration using OT and git diffs as not workable together. Exports and imports, yes. As real backend for the document storage, no.

Not to mention the problem of "how do organize this repository-wise?". One repository per user? One repository per document? One repository per instance? Or do we introduce collections first, which are repositories which then hold the documents? Are they read-only or do we let other people push things there? How do we merge those pushes with the real-time editing?

Git is simply not made for real-time collaboration. And CodiMD is exactly that in first place: A real-time-collaboration tool for markdown."


## References

- https://github.com/hedgedoc/hedgedoc/issues/222
