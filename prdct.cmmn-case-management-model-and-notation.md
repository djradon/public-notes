---
id: krxmaqh11x7obj9erhkwugw
title: Cmmn Case Management Model and Notation
desc: graphical notation used for capturing work methods
updated: 1724192034576
created: 1701196651131
---

## Concepts

- The complete behavior model of a Case is captured in a case Plan Model. 
  - For a particular Case model, a case Plan model comprises of all elements that represent the initial plan of the case, and all elements that support the further evolution of the plan through run-time planning by case workers. 
  - There are four types of Plan Items:

## Description

- There is no model of sequence flow in CMMN. Execution of a task depends on events and conditions called sentries.
  -  A sentry captures the occurrence of a certain event occurring or a condition being fulfilled within a case. 
  -  Sentries are used as entry and exit criteria. Note that the black and white diamonds represent the criteria.

## Issues

- poor adoption
- [[prdct.bpmn]] overlap 

## Comparison

### vs [[prdct.bpmn]]

![](/assets/images/2023-11-28-10-39-20.png)


| Most of BPMN Notations | CMMN Notation |
| --- | --- |
| Imperative | Declarative |
| Process centric | Data centric |
| Arcs describe the sequence | No predefined sequence |
| Guided work (head down workers) | Enables workers (knowledge workers) |
| Everything is modeled | Not everything is modeled |



## Resources

- https://www.processmaker.com/blog/intro-to-case-management-model-and-notation-cmmn/
  - "Business Process Model and Notation (BPMN), Case Management Model and Notation (CMMN), and Decision Model and Notation (DMN) form what is often called the “triple crown” of business modeling notations."


## References

- https://camunda.com/blog/2020/08/how-cmmn-never-lived-up-to-its-potential/
- https://www.flowable.com/blog/business/introducing-the-case-management-model-and-notation-standard-cmmn
- https://www.visual-paradigm.com/guide/cmmn/what-is-cmmn/