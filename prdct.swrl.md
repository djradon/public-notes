---
id: 8t3iauhhd831hud0d68r44o
title: Swrl
desc: 'language for the Semantic Web that can be used to express rules as well as logic, combining OWL DL or OWL Lite with a subset of the Rule Markup Language (itself a subset of Datalog)'
updated: 1715879839875
created: 1710688791666
---

- related: [[prdct.datalog]] [[prdct.ruleml]] [[prdct.sqwrl]]
- spec: https://www.w3.org/submissions/SWRL/


## Issues

- WRL shares OWL’s open world assumption so certain types of rules that assume a closed world may be difficult or impossible to write in SWRL

## References

- https://www.michaeldebellis.com/post/drools-vs-pellet-for-swrl-rules by @michael-debellis
  - the difference between using [[prdct.drools]] and using the [[prdct.pellet]] reasoner and why using Pellet is usually the better option
  - Another excellent use of DROOLS is that it is used to extend SWRL's time built-ins to implement the   for reasoning about time.
- https://github.com/protegeproject/swrlapi/wiki/ModellingTime