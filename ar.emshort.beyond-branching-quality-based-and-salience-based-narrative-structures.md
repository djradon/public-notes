---
id: d1lgob25gzr6brnsoni2e9a
title: Beyond Branching Quality Based and Salience Based Narrative Structures
desc: ''
updated: 1727212255859
created: 1727208714215
---

- https://emshort.blog/2016/04/12/beyond-branching-quality-based-and-salience-based-narrative-structures/
- mentions: [[prdct.storyspace]]

## Highlights

- There is a fair amount of craft writing about how to make branching narrative thematically powerful, incorporate stats, and [avoid combinatorial explosions](https://www.choiceofgames.com/2011/07/by-the-numbers-how-to-write-a-long-interactive-novel-that-doesnt-suck/), as well as just [minimizing the amount of branching relative to the number of choices offered](http://gdcvault.com/play/1023072/All-Choice-No-Consequence-Efficiently). [Jay Taylor-Laird did a talk on branching structures at GDC 2016](http://gdcvault.com/play/1023095/The-Shapes-in-Your-Story), which includes among other things a map of Heavy Rain. And whenever I mention this topic, I am obligated to link [Sam Kabo Ashwell’s famous post on CYOA structures](https://heterogenoustasks.wordpress.com/2015/01/26/standard-patterns-in-choice-based-games/).

### My story is made of pieces of content. How do I choose which piece to show the player next?

- [[[t.story-telling.narratology.quality-based-narrative]] is the term invented by Failbetter Games to refer to [interactive narratives structured around storylets unlocked by qualities](http://www.failbettergames.com/tag/narrative-engineering/). A storylet is typically a paragraph or two of text followed by a choice for the user (each option is referred to as a branch in Failbetter parlance) and text describing the outcome of that choice. Qualities are numerical variables that can go up or down during play, and represent absolutely everything from inventory (how many bottles of laudanum are you carrying?) to skills (what is your Dangerous skill level?) to story progress (how far have you gotten in your relationship to your Aunt?). The StoryNexus tool implements QBN; so did [Varytale](https://emshort.wordpress.com/?s=varytale&submit=Search), while that was still around, though in a hybrid form that allowed storylets themselves to contain CYOA-styled segments.
  - [[prdct.storynexus]] is hard on new authors because the content tends to be uninteresting until there are a fair number of storylets in the database, so it’s hard to feel like you’re really rolling until you’ve spent quite a bit of time in the tool.
- [[t.story-telling.narratology.salience-based-narrative]] is a term I just made up to refer to interactive narratives that pick a bit of content out of a large pool depending on which content element is judged to be most applicable at the moment. Like QBN, this approach is agnostic about what kind of information matters: just as a quality in Fallen London could be pretty much anything, salience narrative can be tied to pretty much any testable information in the world state.
  - relatively easy to build a rudimentary set of content with sensible, broad defaults, and then gradually add new, more salient content for individual situations. ^nt9g9zslhb88
  - It’s not coincidental that both of the “salience-based” applications I mentioned are for triggering dialogue specifically, and that they’re handling a narrative layer transposed on an otherwise explorable environment.
  - A much more extreme version of this is Doug Sharp’s [[game.the-king-of-chicago]] (you should really read this article if you haven’t — it’s fascinating). _The King of Chicago_ is not just generating suitable dialogue but actually sequencing what should happen next in the story from a collection of possible scenes, based on everything that has occurred so far. It’s also using numerical rather than boolean state variables to measure salience.