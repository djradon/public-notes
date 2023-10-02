---
id: imnxtawclhc9hpl80yboqf5
title: Soar
desc: ''
updated: 1696269809580
created: 1694362703008
---

- [[c.Software.Cognitive-Architecture]]
- #url http://soar.eecs.umich.edu/ 
- #repo https://github.com/SoarGroup/Soar
- [[p.writtenIn]] #c++ 


## [[c.Documentation]]

### https://soar.eecs.umich.edu/downloads/Documentation/SoarManual.pdf

#### Ch. 1

- all deliberate goal -oriented behavior can
be cast as the selection and application of operators to a state
- Working memory is organized as objects. 
  - Objects are described in terms of their attributes; the values of the attributes may correspond to sub-objects, so the description of the state can have a hierarchical organization
- A Soar program contains the knowledge to be used for solving a specific task 

##### Types of Procedural Knowledge
1. Inference Rules
In Soar, we call these state elaborations. This knowledge provides monotonic inferences
that can be made about the state in a given situation. The knowledge created by such
rules are not persistent and exist only as long as the conditions of the rules are met.
1. Operator Proposal Knowledge
Knowledge about when a particular operator is appropriate for a situation. Note
that multiple operators may be appropriate in a given context. So, Soar also needs
knowledge to determine which of the candidates to choose:
1. Operator Selection Knowledge:
Knowledge about the desirability of an operator in a particular situation. Such knowl-
edge can be either in terms of a single operator (e.g. never choose this operator in this
situation) or relational (e.g. prefer this operator over another in this situation).
1. Operator Application Rules
Knowledge of how a specific selected operator modifies the state. This knowledge
creates persistent changes to the state that remain even after the rule no longer matches
or the operator is no longer selected.


### https://arxiv.org/ftp/arxiv/papers/2205/2205.03854.pdf

### 

- "The ultimate in intelligence would be complete rationality which would imply the ability to use all available knowledge for every task that the system encounters. Unfortunately, the complexity of retrieving relevant knowledge puts this goal out of reach as the body of knowledge increases, the tasks are made more diverse, and the requirements in system response time more stringent."  ^jxijnmn32t8u
- "Through Soar 8, there has been a single framework for all tasks and subtasks (problem spaces), a single representation of permanent knowledge (productions), a single representation of temporary knowledge (objects with attributes and values), a single mechanism for generating goals (automatic subgoaling), and a single learning mechanism (chunking). We have revisited this assumption as we attempt to ensure that all available knowledge can be captured at runtime without disrupting task performance. This is leading to multiple learning mechanisms (chunking, reinforcement learning, episodic learning, and semantic learning), and multiple representations of long-term knowledge (productions for procedural knowledge, semantic memory, and episodic memory)."
- 