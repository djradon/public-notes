---
id: 5c2dcr4xyptdk8kb22wb0vk
title: >-
  Exploring Advanced Error Handling Patterns with Event Driven Architecture Part
  I
desc: ''
updated: 1713287095228
created: 1713286757856
---

- https://medium.com/ssense-tech/exploring-advanced-error-handling-patterns-with-event-driven-architecture-part-i-e2f37741d904

## Conclusion

event-driven architectures come with the need for more complex error detection and handling.

Assessing whether the trade-off actually pays off is an exercise that you have to do and ultimately your context will dictate if it is the right choice.

If that is the case for you, then revisit where it is applied and look for signs that you should be adopting a choreographed saga to make those errors visible. Then, determine which errors are transient or permanent to tailor your application and achieve a self-healing status as much as possible.

Finally, be aware that dead letter queues, while helpful, have to be treated as first-class citizens of your application. This means ensuring you actively monitor the DLQs and look for ways to improve your application as each root cause of the message is identified.