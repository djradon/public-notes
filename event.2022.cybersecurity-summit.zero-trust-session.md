---
id: nbcb8hr53tlcc8hj5qjn28v
title: Zero Trust Session
desc: ''
updated: 1666905405022
created: 1666903887110
---

- [[p.hadPresenter]] @den-jones
  - has deployed [[t.cs.security.zero-trust-network-access]] with three different technologies
- authentication only focused on the user and ignores the device
- mistakenly consider the corporate network "safe"
- network perimeter no longer a security boundary
- "we don't want to back-haul all the traffic to inspect all the packets"
- make the user experience better
  - "never enter a password again"
    - use a certificate tied to device and user
  - self-remediation
  - no more VPN... "internet facing application, but accessed via reverse-proxy"
- ZTNA
- if you're not using it, remove access
- "access proxy is still a VPN, kinda, but the user never logs in"
- policy engine:
  - if you have a cert, edr, and patches, we let you in
- adobe had 5 data classifications; "smoking crack"
- fewer tools
- suites don't integrate
- IDP was big; 
- "get your cmdb right" is bullshit, could take 20 years
- Get started
  - sell vision, people, process and technology
  - begin with cross-functional core team
  - find a concrete use case
  - start by integration with your existing auth platform
- "executive support is essential"
- introduce zero-trust principles, but avoid the term zero trust
- active communication (use a countdown)
- 