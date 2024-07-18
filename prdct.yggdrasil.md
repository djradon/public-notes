---
id: v9gc1rzp1toqqdn99n4cb0j
title: Yggdrasil
desc: >-
  A framework for programming distributed hypermedia environments for autonomous agents.
updated: 1721337663400
created: 1712555355383
---

- https://interactions-hsg.github.io/yggdrasil/
- repo: https://github.com/Interactions-HSG/yggdrasil
- related: [[prdct.agents-and-artifacts-metamodel]] [[prdct.hyperagents]]
- built_on: [[prdct.vertx]] [[prdct.websub]]
- written_in: java
  
## Architecture

![](/assets/images/2024-04-11-12-47-47.png)

There are four main modules at play in this project. Each contains a component running in its own "event loop," capable of receiving information from others via "events" - read "messages" - onto an "event bus." An event bus is then a shared communication channel between all event loops. Architecture invariant: all the modules must be as decoupled as possible so they cannot communicate directly and synchronously via method calls. They must communicate in an indirect, asynchronous fashion using message passing.

http package

This package contains the "HTTP Server" module, so the HTTP Server that external Web Clients can contact. It exposes the functionalities of the web service through dedicated routes. The routes are in the "HttpServerVerticle" class, while their associated behavior is in the "HttpEntityHandler" class. The server allows the client to create, update, delete, and get environments, workspaces in those environments, and artifacts in those workspaces. For each request, it issues the corresponding operation on the "CArtAgO" component. After its completion, it can create, serialize, and send the representation of the involved entity to the "RDF Store" component. Between the other functionalities, there is one for registering for notifications through the "WebSub" protocol, registration aptly notified from the HTTP Server to the "HTTP Notification" component.

cartago package

This package contains the "[[prdct.cartago]]" module, handling the interactions with the CArtAgO platform to allow compatible agents and frameworks to interact with Yggdrasil. An example is the "JaCaMo" platform, which can connect to remote CArtAgO nodes, such as the one managed by this module, and let its agents interact with it. The "CartagoEntityHandler" handles all the CArtAgO requests coming from the "HTTP Server" module, forwarding them appropriately to the "CartagoVerticle" class. This last one effectively implements the interplay between Yggdrasil and CArtAgO. This class allows workspace creation, artifact creation, and action invocation on artifacts: the operations part of CArtAgO. These entities' construction also means generating their semantic representation as a response to the request to do it, which the "HTTP Server" component then routes to the "RDF Store." All the artifacts created by Yggdrasil are instances of the "HypermediaArtifact" class. It exposes some methods to retrieve and set properties that are proper of "thing descriptions," such as their action affordances, security schemes, et cetera. To keep track of all the artifacts created without passing from CArtAgO, a "HypermediaArtifactRegistry" is used. This registry also handles all the secondary operations, such as getting and setting prefixes, names, and API keys for different entities. This module is also capable of handling the percepts observation. The module continually listens to the CArtAgO platform for new signals or observable property updates and forwards them to the "HTTP Notification" module to inform its subscribers. The only thing this module does not handle is the environment creation because this is not a CArtAgO feature but is an extension brought by Yggdrasil.
store package

This package contains the "RDF Store" module. It is responsible for storing the semantic representations of the environments, the workspaces, and the artifacts. Yggdrasil uses the "Thing Description" ontology to represent these entities. This "knowledge" representation and storage allows agents to crawl the MAS semantically, realizing the "semantic relations" and the single entry-point principle described above. The "RdfStoreVerticle" activates in response to events from the "HTTP Server" module, which events ask to get, create, update, or delete their designated entity. The class forwards the requests to the store, effectively represented by the "RdfStore" interface and its "Rdf4jStore" implementation. After a creation, update, or deletion operation succeeds, the store sends an event to the "HTTP Notification" module to alert all its subscribers. It is also responsible for generating the IRIs of the resources stored and serializing and deserializing the knowledge graphs kept inside of itself.

websub package

This package contains the "HTTP Notification" module. It sends real-time notifications about artifacts' observable property updates or signal firings, as requested by the CArtAgO component. It also sends alerts about changes in the system state, such as entity creations, deletions, and updates, as requested by the HTTP Server component. The class implementing this functionality is the "HttpNotificationVerticle" one. This module implements the "WebSub" protocol for sending notifications to subscribers, a web recommendation for publish-subscribe communication over the Web. A registry of all subscribers is then needed, and the "NotificationSubscriberRegistry" class contains it.


## References

- [[ar.engineering-world-wide-multi-agent-systems-with-hypermedia]]
- [[ar.environment-programming-in-multi-agent-systems-an-artifact-based-perspective]]