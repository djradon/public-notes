---
id: sTBg5mG9Tkq5iYOVDqbcH
title: Foundry-VTT
desc: ''
updated: 1715105028585
created: 1633307850499
---

- [[c.software.rpg.virtual-tabletop]]

## Integrations

- map-imports: [[prdct.Dungeon-Draft]] [[prdct.dungeon-alchemist]]
- content-integrations: [[prdct.WorldAnvil]] [[prdct.dscryb]] [[prdct.syrinscape]] [[prdct.plutonium]]
- others: [[prdct.kanka]] (via [[prdct.kanka-foundry]]) [[prdct.the-only-sheet]] [[prdct.lava-flow]]
- built-on: [[prdct.pixi-js]]

## User Stories

### modding

- "easily it can be modded which puts it's automation above that of what I've witnessed in any other VTT. "
- " there is a thing about platforms where the one that is pretty popular and moddable attracts the best modders, which means it becomes much better and attracts more great modders and users.. Foundry has snowballed to a point where a DM who is a bit technical and wants to add mods has an amazing variety of options. "

### planning

- "I've been enjoying writing my new campaign in Obsidian. Wiki style links and an add on allows for pinnable maps. There are a number of other plug ins specifically for D&D or similar. "
- "I've since moved to running sessions directly off of journal entries. There's nothing better than being able to control the game world with in-line links and scripts"
- "While I love Foundry, I always found a little janky to use it to worldbuild and to take notes. I love using Obsidian and I currently use it to plan my sessions and worldbuild. However, I would very much like to use a single app to all my TTRPG needs."

### GM Website

- "Honestly, I just found the friction of trying to world-build within Foundry too high, even with mods.

So, I have elected to move everything "not nailed down in Foundry" to a website I control (built using Hugo) -- though I strongly considered using [[prdct.legend-keeper]] for a hot-second (but I wanted my files local). So, I just fired up a webserver on the same machine as the foundry server and deployed from a Hugo site I build in VSCode.

Then, in Foundry, I'll have journal entries that are just HTML iframes to particular sites. I mean, hell, my players are already using the browser in Foundry. They might as well be able to leverage the power of browsing while we play, too. The Arc browser makes this a breeze, too, with it's good tab, spaces, and window controls. Edge can do similar.

Now, the only stuff in Foundry really are just the mechanical fiddly bits needed to run the game. Everything else is sitting in the website. And then my private notes/wiki in Obsidian (yes, I tinkered with using Obsidian to manage the website, but I did't like 1. paying the extra fee for Obsidian Publish when I already had a perfectly fine host and 2. I really wanted a lot of control over the player-facing site. Love Obsidian as my GM wiki, though."

## Development

### Module Development

Modules extend and modify the behavior of Foundry Virtual Tabletop and its game systems. At a conceptual level, think of each Module as a "plug-in" or "add-on" which changes the software behavior in small (or large) ways. Modules can alter the behavior of the core software in several different ways:

Content
    Modules which add data in the form of compendium packs of Adventures, Actors, Items, Scenes, Journal Entries, Roll Tables, or Playlists.
Interface
    Modules which change the way the UI looks or behaves, changing the aesthetics and user experience of the software.
Functionality
    Modules which add entirely new functionalities or features which do not exist in the base software, or modules which change the behavior of core features so they behave differently.
Translation
    Modules which add support for translation of text displayed in Foundry VTT into other languages. 

### System Development




## Resources

- https://www.reddit.com/r/FoundryVTT/comments/10gt7jt/what_options_are_there_for_organizing_world/
- https://www.reddit.com/r/FoundryVTT/comments/1asnse4/there_are_modules_to_use_foundry_to_worldbuild/

### Learning Resources

- https://foundryvtt.com/article/module-development/


## References

- https://www.reddit.com/r/FoundryVTT/comments/10mmkj0/where_do_i_start_creating_a_game_system/