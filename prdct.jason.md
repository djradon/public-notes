---
id: vsv0kv6hcorhkp99pkb1y3z
title: Jason
desc: 'an interpreter for an extended version of AgentSpeak'
updated: 1712549096230
created: 1712534710390
---

- repo: https://github.com/jason-lang/jason/
- url: https://jason-lang.github.io/
- related: [[prdct.agentspeak]]
- written_in: java
- works_with: 
  - [[prdct.Jade]]

## features:

-   strong negation, so both closed-world assumption and open-world are available;
-   handling of plan failures;
-   speech-act based inter-agent communication (and belief annotations on information sources);
-   annotations in beliefs used for meta-level information and annotations in plan labels that can be used by elaborate (e.g., decision-theoretic) selection functions;
-   meta events, declarative goal annotations, higher order variables and treating plans as terms, imperative style commands in plan bodies, and various other language extensions;
-   support for developing Environments (which are not normally to be programmed in AgentSpeak; in this case they are programmed in Java);
-   support for MAS organisations and agents that reason about them, using the Moise+ model, and environments using CArtAgO - see the [JaCaMo website](https://jacamo-lang.github.io) for that;
-   the possibility to run a multi-agent system distributed over a network (using [JADE](https://jade.tilab.com)); other distribution infrastructures can be added by the user;
-   fully customisable (in Java) selection functions, trust functions, and overall agent architecture (perception, belief-revision, inter-agent communication, and acting);
-   a library of essential “internal actions”;
-   straightforward extensibility by user-defined internal actions, which are programmed in Java;
-   various ways of developing and running code include IDEs and a “mind inspector” that helps debugging.
-   

## References

- [[ar.programming-jade-and-jason-agents-based-on-social-relationships-using-a-uniform-approach]]
