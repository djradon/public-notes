---
id: zqh4p0cz044lzzvgfmmpogn
title: >-
  Programming Jade and Jason Agents Based on Social Relationships Using a
  Uniform Approach
desc: ''
updated: 1712554728337
created: 1712549097190
---

- url: https://www.lancaster.ac.uk/~chopraak/mfsc-2015/baldoni.pdf
- topic: [[prdct.Jade]] [[prdct.jason]]

## Abstract

2COMM as a framework for defining social relations among parties, represented by social commitments. Starting from the definition of interaction protocols, 2COMM allows to decouple interaction design from agent design, an advantage that simplifies agent programming, in- dependently of the chosen agent platform. A comparison between real implementations using 2COMM is provided for JADE and Jason agents.


## Highlights

- In order to reify the social relationships we rely on the [[Agents & Artifacts meta-model (A&A)|prdct.agents-and-artifacts-metamodel]] 

### Modeling Social Relationships

- We propose to explicitly represent social relationships among the agents. By social relationships we mean normatively defined relationships, between two or more agents, resulting from the enactment of roles, and subject to social control. Thus, we encode social relationships as commitments. A commitment [19] is rep- resented with the notation C(x, y, r, p), capturing that the agent x commits to the agent y to bring about the consequent condition p when the antecedent con- dition r holds. Antecedent and consequent conditions generally are conjunctions or disjunctions of events and commitments. When r equals >, we use the short notation C(x, y, p) and the commitment is said to be active. Commitments have a regulative nature, in that debtors are expected to behave so as to satisfy the engagements they have taken. This practically means that an agent is expected to behave so as to achieve the consequent conditions of the active commitments of which it is the debtor.

- it's necessary to provide the agents the means to create, to manipu- late, to observe, to monitor, to reason, and to deliberate on social relationships. We do so by exploiting properly defined artifacts, that reify both interaction pro- tocols, defined in terms of social relationships, and the sets of social relationships, that are created during the protocols execution, available to agents as resources

  -  The semantics of the social actions is given in terms of commitment operations (as usual for commitments, create, cancel, release, discharge, assign, and delegate).
-  From an organizational perspective, a protocol is structured into a set of


## References

- [[ar.agents-and-artifacts-a-meta-model-for-agent-oriented-computing]]

We assume that roles cannot live autonomously: they exist