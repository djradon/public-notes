---
id: hm1p8m9ly06hutd4acobasj
title: TTRpg
desc: 'ontologies for rpgs'
updated: 1723911182982
created: 1710802467257
---

- [[c.ontology]] [[c.ontology.domain]] [[c.ontology.domain.rpg]]
- author: @ruben-wambacq
- ontology:
  - https://github.com/rwambacq/TTRpg/blob/master/TTRpg.ttl
  - https://github.com/rwambacq/DnD5eCharacter/blob/master/DnD5eCharacter.ttl
- related: [[prdct.DnD5eCharacter]]

## Issues

- small
- no sample data, although [[prdct.DnD5eCharacter]] 
- items, creatures, and locations don't have a common superclass
- "knows" only refers to spells, i.e., bad predicate naming
- "type" is overloaded for characters, spells, and items
  - `CharacterType` isn't really used, except as the range of `type`

- "hasItem" has domain World
- `Player` is subclass of `foaf:Person` instead of `foaf:Agent`
- `Weapon` is a subclass of `ItemType` which might work out okay if its sense is WeaponType,