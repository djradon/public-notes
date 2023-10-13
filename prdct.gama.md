---
id: yfdmxrwjycaz3db8uswe0b5
title: Gama
desc: ''
updated: 1697091631073
created: 1694708152058
---

- [[c.Software.Agent-Framework]] [[c.Software.Cognitive-Architecture]]
- #url https://gama-platform.org/
- #repo https://github.com/gama-platform/gama
- [[p.writtenIn]] #java
- [[p.implements]] [[prdct.FIPA.ACL]]
  - https://gama-platform.org/wiki/UsingFIPAACL
- 

## #features

- [[prdct.FIPA]], see https://gama-platform.org/wiki/1.8.1/UsingFIPAACL
- supports [[t.cs.agents.bdi]] via [[prdct.gama.ben]]
## [[c.Thought]]

- seems overly-attached to the UI; 
  - [headless mode](https://gama-platform.org/wiki/Headless-mode-for-dummies) is experiment-oriented, not interactive
    - [[p.hadLimitation]]
      - close the socket on client-side) gama-server will destroy all running simulations of that client, so you have to keep your client alive.
      - communicates via websocket only? i.e., no http/s or grpc
      - 

## [[c.Example]]

- [Kiss Nightclub simulation](https://www.comses.net/codebases/7ca5fbb1-9e3a-4ea1-a63f-87d2ba9f39d6/releases/1.1.0/)
- [LittoSIM-GEN: a serious game of flooding risk management](https://hal.science/hal-03519918/)
- [Sprite](https://sites.google.com/site/caroleadamphd/development/sprite)
  - https://drive.google.com/file/d/12J6Wyr1DBqvRXfH5xWQNWRNpNiWhIyHt/view

## [[c.Resource]]

### [[c.Resource.Learning]]

- https://unigis-salzburg.github.io/Opt_Spatial-Simulation/


### [[c.Comparison]]

- [[An Initial Comparison of Selected Agent Based Simulation Tools in the Context of Industrial Health and Safety Management|ar.acm.an-initial-comparison-of-selected-agent-based-simulation-tools-in-the-context-of-industrial-health-and-safety-management]]
