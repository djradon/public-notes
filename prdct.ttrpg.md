---
id: hm1p8m9ly06hutd4acobasj
title: TTRpg
desc: 'ontologies for rpgs'
updated: 1710802951638
created: 1710802467257
---

- author: @ruben-wambacq
- ontology:
  - https://github.com/rwambacq/TTRpg/blob/master/TTRpg.ttl
  - https://github.com/rwambacq/DnD5eCharacter/blob/master/DnD5eCharacter.ttl
- related: [[prdct.DnD5eCharacter]]

## Issues

- items, creatures, and locations don't have a common superclass
- "knows" only refers to spells, i.e., bad predicate naming
- "type" is overloaded for characters, spells, and items
- "hasItem" has domain World
- 