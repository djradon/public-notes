---
id: n9caaxapx6uup4g1225fqcx
title: Simulation Time
desc: ''
updated: 1673914878928
created: 1673914705265
---

## Resources

- https://support.tetcos.com/support/solutions/articles/14000057035-what-is-simulation-time-
  - Therefore, simulation time is not allowed to progress during an event, but only between events. In fact, the simulation time is always equal to the time at which the current event occurs. Therefore, simulation time can be viewed as a variable that "jumps" to track the time specified for each new event.
  - Note that when running in "Emulation mode" simulation time and wall clock will be exactly synchronized since it involves the transfer of real packets across the virtual network in NetSim.