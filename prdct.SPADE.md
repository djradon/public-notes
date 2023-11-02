---
id: 7YhDqhSgMhMtHv5SQqjil
title: SPADE
desc: ''
updated: 1698953779839
created: 1637794683065
---

- [[c.software.agent-framework]] but "platform-less"
- [[p.hasRepository]] https://github.com/javipalanca/spade
- [[p.hasSite]] https://spade-mas.readthedocs.io
- [[p.writtenIn]] #python
- [[p.builtOn]] [[prdct.xmpp]]
  - there's a matrix-xmpp bridge, and even more abandoned https://matrix.org/docs/projects/bridge/matrix-appservice-prosody
  - [[prdct.cloudevents]] has an XML spec: https://github.com/cloudevents/spec/blob/main/cloudevents/working-drafts/xml-format.md
- [[p.isRelated]] [[prdct.spade.pubsub]] [[prdct.spade.bdi]] [[prdct.spade.artifact]]

## Features

- "you can develop your own agents in the programming language of your choice and use them with SPADE. The only requirement those agents must fulfill is to be able to communicate through the XMPP protocol."
- "SPADE 3 is not planned to be FIPA compatible" but "Supports FIPA metadata using XMPP Data Forms "
- "Currently there is no AMS or DF in SPADE, which are the agents that allow to search for other agents or services in JADE (FIPA, really). This is due to SPADE's platform-less approach, which tries to have a very small and fast core. However, the possibility of creating plugins for SPADE is explained in the documentation, so, if you think this is an interesting feature: just write a plugin! :)"
## Comparison

[[vs.spade-vs-pade]]

## Resources

- https://github.com/javipalanca/spade/issues/54#issuecomment-475730896
  - 