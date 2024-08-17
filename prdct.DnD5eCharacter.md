---
id: aai8poey1tnk6kd65ruxg45
title: DnD5eCharacter
desc: ''
updated: 1723911515662
created: 1711286402617
---

- [[c.ontology]] [[c.ontology.domain]] [[c.ontology.domain.rpg.dnd]]
- https://github.com/rwambacq/DnD5eCharacter/blob/master/DnD5eCharacter.ttl

## Thoughts

- [[prdct.owl.full]], e.g.
  - class CureWounds DnD5eCharacter:inMagicSchool DnD5eCharacter:Evocation ;

## Issues

- "armor" 
  - seems to represent types of armor
  - isn't a subclass of anyting, including [[prdct.ttrpg]]'s ItemType.Armor
- Monster is a CharacterType, along with AbilityScore and Skill
- Character seems redundant with ttrpg:Character, doesn't have any superclass or details
- creates a custom "version" property to keep track of ontology version