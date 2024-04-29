---
id: lkrtyir3nc1ujpqk3rf5uep
title: Enabling Retroactive Computing through Event Sourcing
desc: ''
updated: 1713482621936
created: 1713482051787
---

- https://oparu.uni-ulm.de/server/api/core/bitstreams/169d77df-ea1a-4e5a-8322-148e309f2ee9/content
- topics: [[t.cs.data.temporality.retroactive-computing]]


## Abstract 
Event sourcing is a style of software architecture wherein state altering operations to an application are captured as immutable events. Each event is appended to an event log, with the current state of a system derived from this series of events. This thesis addresses the utilization of retroactive capabilities in event-sourced systems: comput- ing alternate application states, post hoc bug fixes, or the support of algorithms which have access to their own history, for example. The possibility of retroactively access- ing and modifying this event log is a potential capability of an event-sourced system, but a detailed exploration how these operations can be facilitated and supported has not yet been conducted. 

We examine how retroaction can be applied to event-sourced systems and discuss conceptual considerations. Furthermore, we demonstrate how different architectures can be used to provide retroaction and describe the prototypical implementation of an appropriate programming model. These findings are applied in the Chronograph research project, in order to utilize potential temporal aspects of this platform.


## References

- https://conf.researchr.org/details/debs-2017/debs-2017-papers/1/Chronograph-A-Distributed-Processing-Platform-for-Online-and-Batch-Computations-on-Ev