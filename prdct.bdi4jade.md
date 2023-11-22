---
id: 95anc8rs4xyj8pmrbw06cpb
title: Bdi4jade
desc: ''
updated: 1698252759203
created: 1694457296870
---

- repo: https://github.com/ingridnunes/bdi4jade

## Features

- BDI abstractions 
- reasoning cycle
-   **Use of Capabilities** – agents aggregate a set of capabilities, which are a collection of beliefs and plans, and allow modularisation of particular agent functionality.
-   **Plan Body is an Extension of JADE Behaviour** – in order to better exploit JADE features, plan bodies are subclasses of JADE behaviours.
-   **Java Annotations** – annotations are provided to allow easier configuration of agent components, without compromising its flexibility.
-   **Extension Points** – strategies can be easily implemented to extend parts of the reasoning cycle, such as belief revision and plan selection.
-   **Listeners and Events** – different events (such as events related to goals and beliefs) can be observed in the platform, allowing listeners to react according to events that occurred.
-   **Java Generics for Beliefs** – beliefs can store any kind of information and are associated with a name, and if the value of a belief is retrieved, it must be cast to its specific type, so the use of Java generics allows us to capture incorrect castings at compile time.