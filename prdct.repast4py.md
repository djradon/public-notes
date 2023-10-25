---
id: ud3oq1w0uu5pj702m9kjbbr
title: Repast4py
desc: ''
updated: 1696350842895
created: 1694617862020
---

- [[c.Software.Agent-Framework]] [[c.Software.Simulation-Framework]]
- #repo https://github.com/Repast/repast4py

## Thoughts

- "distributed" means that the simulation is spread over multiple computer processes none of which have access to each other’s memory, and communicate via message passing using the [[Message Passing Interface|prdct.mpi4py]].


## Resources

- [DISTRIBUTED AGENT-BASED SIMULATION WITH REPAST4PY](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9912342/)
  - "the user must implement a save method that returns the state of the agent as a tuple."
    - hah! how about a reference to save state
  - event scheduling
    - "events are scheduled to occur at a particular tick. Ticks do not represent clock-time but rather the priority of its associated event"
    - A floating point tick, together with the ability to order the priority of events scheduled for the same tick, provides for flexible scheduling.
  - "components are of three types: 1) agents and their environments; 2) logging and data collection; and 3) simulation utility functions (e.g., random number management, input parameter parsing, and so on)"