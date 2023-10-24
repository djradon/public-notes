---
id: hqlgs32wh67aak9kh6258l0
title: Memphis Dev
desc: ''
updated: 1698175338725
created: 1698086020054
---

- [[p.asked]] Does anyone know if Memphis and Memphis Cloud have websocket (i.e., browser) support? There's https://github.com/nats-io/nats.ws and given that Memphis has NATS at its core, it seems like it might be possible?
  - https://discord.com/channels/963333392844328961/1114471626210299975/1166085083795566683
  - @yaniv-ben-hemo : Not at the moment. In case its a must, would love to explore ways to prioritize it


#t.2023.10.24.12

djradon — Today at 11:49 AM
I've been looking for a messaging solution for my product-dream for a while, and was looking at NATS as a "better Kafka", so then naturally stumbled onto Memphis.
Yaniv Ben Hemo — Today at 11:51 AM
Thank you, thats great
Memphis definetly removes much of the heavy-lifting both Kafka and NATS reveal
Can I ask about the use case? Why WS is needed?
djradon — Today at 12:19 PM
Sure! I'm working on a role-playing platform. Not a game, but a way for people to create and play their own games/experiences. So, among other things, it's an agent-based framework where people can build and share their characters, plot lines, societies, and worlds. 

Ideally, people will be able to run their own agents, or spawn agents written by others (i.e., directly from github) into a browser. That way, people don't need to run a node.js server locally. We wouldn't want to run arbitrary code in the game service, so just providing access to a queue for agent commands/intent  from the browser and having browser-based agents collecting "world update events" and sensory data events from other queues provides a clean separation for agent self-hosting. 
