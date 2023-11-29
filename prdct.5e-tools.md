---
id: tij5kl2lv4gzr3tz2kdq147
title: 5e Tools
desc: ''
updated: 1701284069207
created: 1696521323235
similar_to: [[prdct.open5e]]
---

- [[c.software.game-service.data]]
- url: https://5e.tools
- repo: https://github.com/5etools-mirror-1/5etools-mirror-1.github.io
- #docs https://wiki.tercept.net/en/home
- [[p.builtOn]] [[prdct.node]]
- written-in: javascript
- 

## Examples

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
