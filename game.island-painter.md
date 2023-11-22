---
id: mz7sp3coxud111mux0jb7c3
title: Island Painter
desc: not so much a game as a multi-user canvas
updated: 1698275345024
created: 1672226103575
---

repo: https://github.com/darraghjburke/IslandPainter
url: https://darraghjburke.github.io/IslandPainter/ (broken t.2022.12.28)

- [[p.builtOn]]
  - [[prdct.babylon-js]]
  - [[prdct.colyseus]]
  - [[prdct.express]]

## [[p.hasLog]]

### t.2022.12.29 
  
- got running locally, needed `nvm use 16` and
  - ` netsh interface portproxy add v4tov4 listenport=2567 listenaddress=0.0.0.0 connectport=2567 connectaddress=172.19.4.95`
  - ` netsh interface portproxy add v4tov4 listenport=3000 listenaddress=0.0.0.0 connectport=3000 connectaddress=172.19.4.95`