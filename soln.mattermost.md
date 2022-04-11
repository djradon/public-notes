---
id: q469lum2qr1r0cqoko919ck
title: Mattermost
desc: ''
updated: 1649603693183
created: 1649603693183
---

- [[can be extended by|p.hasExtensionMechanism]]
  - plugin
    - [[p.hadAtLeastOneOf]] 
      - server component 
        - runs as a server subprocess
        - [[p.writtenIn]] [[t.cs.language.go]]
      - "web app" component
        - included in page, runs alongside the Mattermost web app code
          - desktop app is shim of web app
        - [[p.writtenIn]] [[t.cs.language.JavaScript]]
        - [[p.builtOn]] 
          - [[soln.React]]
          - [[soln.redux-js]]
  - app
    - lightweight interactive "add-ons" 
    - in any language
    - receive webhooks from mattermost and 3rd-parties
    - use Mattermost REST APIs to post messages
    - attach them selves to locations the user

