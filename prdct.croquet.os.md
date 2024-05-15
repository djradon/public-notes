---
id: 7sn9ivupnu1642udjf7czhj
title: CroquetOS
desc: 'synchronization system for multiuser Metaverse experiences'
updated: 1715718503175
created: 1696289301886
---

- [[c.software.virtual-reality]]
- url: https://croquet.io/croquet-os/
- supports: [[prdct.wordpress]]
- related: [[prdct.croquet.microverse-builder]]

## Features

- multi-user [[c.software.live-programming]]
- "time-based OS": A shared simulation requires not just that external events are propagated between the instances of the shared VM, but these events have an associated time stamp provided by the Croquet Reflector. This ensures that events occur and are processed at the same virtual time for all participants in a session. Secure event/message distribution 
- Applications are structured into a shared and a local part, but both parts are executed locally and developed using only client-side tools.

## Thoughts

- perfectly synced worlds doesn't seem optimal, since users don't all need the whole thing


## Architecture

- reflector runs somewhere on the internet
- kernel is replicated virtual machine that runs bit-identical on all client systems
- locally-rendered view
- events/messages are sent to reflector, sends to kernels
- 