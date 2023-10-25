---
id: s9536b7l08atc8lzmhkotdx
title: Discrete Event Simulation
desc: ''
updated: 1695417262695
created: 1695417250681
---

- In event-based simulation, the entities all run in a single thread. At the time of making a request, the entities provide a callback function that must be invoked when the waiting condition is over. This style of programming is widely used in Graphical User Interface designs where preconfigured callback functions are called by the system when any event of interest occurs (e.g. mouse click).
- The proponents of process-based programming claim that their design leads to a better readability of code. Whereas the adherents of event-based programming argue that their approach is more structured since the actions for each different kind of events are encapsulated as different functions.
  - https://simjs.z5.web.core.windows.net/basics.html#basics-design

## Resources

- https://softwaresim.com/blog/a-gentle-introduction-to-discrete-event-simulation/