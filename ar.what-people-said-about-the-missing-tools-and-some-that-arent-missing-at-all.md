---
id: e6tyj67hjlxa5epcyhmv56a
title: What People Said about the Missing Tools and Some That Arent Missing at All
desc: ''
updated: 1727174307872
created: 1727174251700
---

- https://emshort.blog/2014/03/29/what-people-said-about-the-missing-tools-and-some-that-arent-missing-at-all/
- related: [[event.ludum-dare]]

## Highlights

- **A system supporting multiplayer IF**, especially something resembling the Twine MMO [Naked Shades](http://www.ludumdare.com/compo/2013/04/30/naked-shades-the-worlds-first-twine-mmo/). Andi McClure mentioned that she is working on a relevant toolset. There are also a few other extant multiplayer options: [Guncho](http://www.guncho.com/) is an open-source MUD allowing for multiplayer Inform games, while [Fallen London](http://fallenlondon.storynexus.com/signup?RouteValueDictionary=Syste) offers some features for social interaction between players. There’s also [The Yawhg](http://www.theyawhg.com/), a 1-to-4-player CYOA that came out recently (Windows only, alas, so I haven’t had a chance to play it yet). However, I think it’s fair to say that there aren’t any toolsets that are in very widespread use for this. ^a33tby9d5vda
- **Tools for more systematic, simulationist, or procedural games**. IF games have mostly not done much with procedurally generated worlds and maps, autonomous character behavior, and RPG-like features... 
  - For parser-based games, heavy simulation or randomization also means that the parser has to be more sophisticated about how it interprets noun phrases. Inform gets part of the way there by being able to understand object properties as part of the object’s name, but overall, this needs to be able to track exactly with whatever text generation tricks we’re doing. If we’re calling any short, wide object “stumpy”, then the parser needs to know to read “stumpy” as referring to short wide things. Moreover, the bigger and more complicated the text simulation work we’re doing, the more important that the author doesn’t have to write gazillions of lines of code of the form “Understand “stumpy” as a thing if it is short and wide.” — that becomes unmaintainable. We need, in other words, a more systematic and high-level way of expressing these ideas.
    - [[p.provokedThoughts]]
      - i.e., a collective, open, composable ontology; probably the predicate templates could be universal; synonymy is a gradient 
- For Inform specifically to handle the back-end simulations well, it would likely need dynamic object generation (a long-running request, with an impressive 65 votes on the Uservoice tracker).

