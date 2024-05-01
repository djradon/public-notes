---
id: 878kg6rkvxkaldjauswgqk5
title: Agents and the Semantic Web
desc: ''
updated: 1712599443140
created: 1712599253213
---

- url: https://www.nku.edu/~foxr/CSC625/NOTES/agents.ppt

## Types of Environments

* Accessible vs. inaccessible:  agent’s sensors give it access to the complete state of the environment at each point in time
* Deterministic vs. non-deterministic:  next state of the environment is completely determined by the current state and the action executed by the agent
* Episodic vs. non-episodic:  agent’s experience is divided into atomic episodes, each episode consisting of a perception-action pair where the action is a single action/event
* Static vs. dynamic:  environment is unchanged during the agent’s deliberation of an action
* Discrete vs. continuous:  limited number of distinct, clearly defined percepts and actions
* Single agent:  the agent works in isolation (no other agents around)

## Types of Agents

Reflex Agent
simplest form,  the agent merely reacts to its environment – no memory, no internal states, no planning

State-based Agent
the next step up is an agent that keeps track of its current (and possibly previous) state(s), this can help with planning and understanding

Goal-oriented Agent
this agent has the ability to plan out a sequence of states to achieve in order – planning might be based on a table-lookup approach or something more elaborate using a search mechanism and available planning knowledge

Utility-based Agent
the agent has the ability to determine the usefulness of a plan step toward achieving its goals so that it can achieve the goals in a more optimal fashion, and possibly have better final results for goal

![](/assets/images/2024-04-08-11-04-02.png)