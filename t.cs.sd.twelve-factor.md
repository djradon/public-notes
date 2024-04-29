---
id: 0bfm0r06b2elp3bvkptsqt1
title: Twelve Factor
desc: ''
updated: 1714422586469
created: 1714421794508
---

- https://12factor.net/

## Summary

## I. Codebase: One codebase tracked in revision control, many deploys

-  there should be a one-to-one correlation between an application and its codebase.
- If an application consists of multiple repositories (each with a different root commit), it is considered a distributed system rather than a single 12-factor app.
- To adhere to the 12-factor principles, shared code (common functionality) should be factored into libraries that can be included via a dependency manager.

## II. Dependencies: Explicitly declare and isolate dependencies


## III. Config: Store config in the environment


## IV. Backing services: Treat backing services as attached resources


## V. Build, release, run: Strictly separate build and run stages


## VI. Processes: Execute the app as one or more stateless processes


## VII. Port binding: Export services via port binding

- The twelve-factor app is completely self-contained and does not rely on runtime injection of a webserver into the execution environment to create a web-facing service.

## VIII. Concurrency: Scale out via the process model


## IX. Disposability: Maximize robustness with fast startup and graceful shutdown


## X. Dev/prod parity: Keep development, staging, and production as similar as possible


## XI. Logs: Treat logs as event streams


## XII. Admin processes: Run admin/management tasks as one-off processes