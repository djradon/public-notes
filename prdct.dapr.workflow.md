---
id: ugv0jxysva0668naopc7zvx
title: Workflow
desc: 'makes it easy for developers to write business logic and integrations in a reliable way'
updated: 1707779775308
created: 1694754855598
---

The durable, resilient Dapr Workflow capability:

-   Offers a built-in workflow runtime for driving Dapr Workflow execution.
-   Provides SDKs for authoring workflows in code, using any language.
-   Provides HTTP and gRPC APIs for managing workflows (start, query, pause/resume, raise event, terminate, purge).
-   Integrates with any other workflow runtime via workflow components. (!)

## Details

- Because the workflow engine will replay the workflow several times, the workflow code must be deterministic. This means that each time the workflow replays, the code must behave in the same way as the initial execution, and any arguments used as activity inputs should stay the same.
- Any non-deterministic code should go into activities. This includes, calling other (Dapr) services, state stores, pub/sub systems, and external endpoints. The workflow should only be responsible for the business logic that defines the sequence of the activities.


## Resources

- https://www.diagrid.io/blog/authoring-dapr-workflows-in-dotnet