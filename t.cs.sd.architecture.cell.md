---
id: 1qpleih1ss9tzbjti0v88b9
title: Cell
desc: 'split your system into cells, a collection of components, grouped from design and implementation into deployment. A cell is independently deployable, manageable, and observable'
updated: 1700495567529
created: 1700495349102
---


## Description

- "A cell is a collection of components, grouped from design and implementation into deployment. A cell is independently deployable, manageable, and observable. Components inside the cell can communicate with each other using supported transports for intra-cell communication. External communication must happen through the edge-gateway or proxy, which provides APIs, events, or streams via governed network endpoints using standard network protocols.

A cell can have 1:n components grouped. Components inside the cells are reusable and can instantiate in multiple cells. The cell should document its offers. The capabilities of a cell must be network accessible endpoints. In addition, if the cell needs access to external dependencies, then these must also be exposed as network endpoints through a cell-gateway. These endpoints can expose APIs, events, or streams. Any interfaces that the microservices or serverless components offer that are not made available by the control point should be inaccessible from outside the cell. Every component within the cell should be versioned. The cell should have a name and a version identifier. The versions should change when the cell’s requirements and/or offers change."


## References

- https://medium.com/@raphael.moutard/forget-your-microservices-the-unparalleled-benefits-of-pool-architecture-63b462989856