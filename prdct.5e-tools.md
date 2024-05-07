---
id: tij5kl2lv4gzr3tz2kdq147
title: 5e Tools
desc: ''
updated: 1715107932575
created: 1696521323235
similar_to: [[prdct.open5e]]
---

- [[c.software.game-service.data]]
- url: https://5e.tools
- repo: https://github.com/5etools-mirror-1/5etools-mirror-1.github.io
- #docs https://wiki.tercept.net/en/home
- [[p.builtOn]] [[prdct.node]]
- written-in: javascript
- similar: [[prdct.5e-tools]] [[prdct.open5e]] [[prdct.dnd-5e-srd]] [[prdct.foundry.dnd5e]]  ^vt5y8u6whgr9

## Examples

source: https://github.com/5etools-mirror-2/5etools-mirror-2.github.io/blob/d16f8386835509b6cd3ff9dda9e07f4379e837c6/data/spells/foundry.json#L715

```
		{
			"name": "Melf's Acid Arrow",
			"source": "PHB",
			"system": {
				"damage.parts": [
					[
						"4d4[immediate]",
						"acid"
					],
					[
						"(@item.level)d4[end of turn]",
						"acid"
					]
				],
				"scaling.mode": "none",
				"scaling.formula": ""
			}
		}
```
