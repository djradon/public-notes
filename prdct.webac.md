---
id: vis20c3ycnp7qt6vauquksh
title: WebAC
desc: 'Web Access Control is a decentralized cross-domain access control system.'
updated: 1712763428910
created: 1712762789300
---

- spec: https://solid.github.io/web-access-control-spec/
- related: [[prdct.fedora]]

## features:

- The resources are identified by URLs, and can refer to any web documents or resources.
- It is declarative -- access control policies live in regular web documents, which can be exported/backed easily, using the same mechanism as you would for backing up the rest of your data.
- Users and groups are also identified by URLs (specifically, by WebIDs)
- It is cross-domain -- all of its components, such as resources, agent WebIDs, and even the documents containing the access control policies, can potentially reside on separate domains. In other words, you can give access to a resource on one site to users and groups hosted on another site.