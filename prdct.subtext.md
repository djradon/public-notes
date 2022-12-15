---
id: cp7ybekm5ikxrikg4glged6
title: Subtext
desc: ''
updated: 1653256680546
created: 1653256544493
---


[[p.hasRepository]] https://github.com/subconsciousnetwork/subtext
- [[p.hasComparison]]
  - [[prdct.markdown]]
    - Why not Markdown?

      I took a deep breath before thinking about the jump from Markdown. If you’re a programmer, Markdown is a de-facto standard for formatted text. For many, it is the first obvious choice for this kind of thing. So why Subtext?

      Subtext has evolved out personal experiments with plain-text note-taking, spanning 10 years and 12k notes. Many of these notes are written in Markdown. However, over time, I noticed that my markup needs for note-taking were different from my markup needs for publishing. My note-taking style organically converged on a tiny subset of Markdown's features: text, links, lists, quotes, and one level of heading. To have more may be useful for publishing, but is often overkill for note-taking.

      At the same time, I began to write small generative programs that worked with this collection of notes, little scripts that would combine ideas, remix notes, algorithmically generate new notes… these were the seeds that would later become Subconscious.

      Here, I started to run into limitations with Markdown and HTML. As a complex publishing format, it is unclear how to meaningfully decompose or merge Markdown/HTML documents. When you combine documents, heading levels may need to be changed, lists may need to be flattened or nested. Because the document format is complex, foreknowledge of the meaning of the document is necessary to make meaningful changes. That limits what you can do with software.

      Subtext is an attempt to resolve the problem by radically simplifying it. Paradoxically, by limiting the format to a flat list of blocks, we radically expand what software can usefully do with it. Blocks are easy to parse, easy to work with, and you can do all sorts of interesting generative algorithmic things with them.

      The syntax is also simple, and hard to mess up, and I’m happy about that, too.
