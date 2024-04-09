---
id: s9536b7l08atc8lzmhkotdx
title: Discrete Event Simulation
desc: ''
updated: 1712683410520
created: 1695417250681
---

- In event-based simulation, the entities all run in a single thread. At the time of making a request, the entities provide a callback function that must be invoked when the waiting condition is over. This style of programming is widely used in Graphical User Interface designs where preconfigured callback functions are called by the system when any event of interest occurs (e.g. mouse click).
- The proponents of process-based programming claim that their design leads to a better readability of code. Whereas the adherents of event-based programming argue that their approach is more structured since the actions for each different kind of events are encapsulated as different functions.
  - https://simjs.z5.web.core.windows.net/basics.html#basics-design

## NetLogo

Discrete event scheduling is most useful for models where agents spend a lot of time sitting idle despite knowing when they need to act next. Sometimes in a NetLogo model, you end up testing a certain condition or set of conditions for every agent on every tick (usually in the form of an “ask”), just waiting for the time to be ripe…. this can get cumbersome and expensive. In some models, you might know in advance exactly when a particular agent needs to act. Dynamic scheduling cuts out all of those superfluous tests. The action is performed only when needed, with no condition testing and very little overhead.

For example, if an agent is a state machine and spends most of the time in the state “at rest” and has a predictable schedule that knows that the agent should transition to the state “awake” at tick 105, then using a dynamic scheduler allows you to avoid code that looks like: “if ticks = 105 [ do-something ]”, which has to be evaluated every tick!

A second common use of discrete event scheduling is when it is important to keep track of exactly when events occur in continuous time, so the simplifying assumption that all events happen only at regular ticks is not appropriate. One classic example is queuing models (e.g., how long customers have to stand in line for a bank teller), which use a continuous random number distribution (e.g., an exponential distribution) to determine when the next agent enters the queue.



## Resources

- https://softwaresim.com/blog/a-gentle-introduction-to-discrete-event-simulation/

## References

- https://ccl.northwestern.edu/netlogo/docs/time.html