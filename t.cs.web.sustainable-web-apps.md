---
id: wqm09s60dkxpcrex3ms3j6c
title: Sustainable Web Apps
desc: ''
updated: 1717084229328
created: 1717082727971
---

- related: [[prdct.m-ld]]

## why do so many existing apps lock-in their users and their attention, and keep control over their users' personal data?

First: there is an economic incentive to developing apps without these properties. Data is valuable, and companies who produce applications would prefer to have access to as much of it as possible. Active users are valuable, as they produce valuable data, and are also available to target with another revenue source, advertising. Thus, the more an application developer can keep users and their data tied to a platform, the more that application will succeed economically—that is, until and unless the users demand an alternative. However, it's hard for users to make much progress simply asking for change; the most effective way for users to make their needs known is to actually leave the services they disagree with in favor of those which treat them better, and to do that, there must be alternatives available to move to.

Thus, the second reason: there is a technological disincentive. It's simply much easier to develop an application in which everyone's data is centralized in a database under the application developer's control. Exposing that data via some sort of API is a good deal of extra effort that can be hard to justify. Interchanging data with other applications, to the point of eliminating lock-in, is even harder to justify, as it both gives users a route to leave the application and is even harder to build than simply exposing the data in some ad-hoc format.

## Architecture

![](/assets/images/2024-05-30-08-50-20.png)

-   The JavaScript code and other static assets of the Web App (the _app_, in pink) are served from some origin via HTTP.
-   The app establishes a working Graph Model, comprised of _semantic web_ data \[\[RDF-NOT\]\] (non-specific serialisation).
-   The Graph is stored locally, and so is available without a network round-trip (unless it has to be fetched to get started!). It is local-first \[\[LOFI\]\].
-   If other replicas of the Graph exist elsewhere, they are synchronised, when the network is available, via a Message Delivery service.
-   If desired for data safety, the Graph can also be replicated to a Backup service, having its own persistent storage.
-   Such a Backup service may also expose the data in the Graph as Linked Data \[\[LINKED-DATA\]\] via its own API. This makes the data de-referencable, via HTTP, for more loosely-coupled consumers.

## References

- https://github.com/m-ld/sustainable-web-apps/blob/main/spec/index.md
- https://github.com/m-ld/sustainable-web-apps/blob/main/spec/design/architecture.md