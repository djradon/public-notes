---
id: 3k2eyrc8wnr1pjktij6yke1
title: Video Game Ontology
desc: ''
updated: 1712266609874
created: 1712255421910
---

- dead since 2015
- url: http://vocab.linkeddata.es/vgo/
- repo: https://github.com/dgarijo/VideoGameOntology
- uses: [[prdct.lode]]

![](/assets/images/2024-04-04-11-41-00.png)

## Overview

Classes

    Achievement Character Collection Completion Curiosity Fandom Feature Gain event Game Game event Game Product Genre Hard mode In-app purchase event Instantaneous event Item Leaderboard Lose event Loyalty Luck Menu event Minigame Multiplayer Paragon Player Player event Playing area Session Special play style Tutorial Veteran Virtuosity 

Properties

    creator has feature has game genre has leaderboard has playing area is achieved in session is achievement in game is character in game is character in session is event associated to player is event in game is event in session is event related to item is event triggered by character is friend with player is item in game is player in session is session in game lives in owns achievement owns character owns item plays game purchases game offering unlocks achievement 

Data Properties

    end Time event Time event Name release Date start Time username 

## Issues

- http://purl.org/net/VideoGameOntology#Item does differentiate between abstract items from one that is actually encountered
  - the example of "Potion" is more like ItemType
- http://purl.org/net/VideoGameOntology#LoseEvent doesn't differentiate between an agent losing something and a character losing something. 
  - superclasse GameEvent says "GameEvent describes an event that takes place in a game without straight player interaction" but a LoseEvent example is "a player can lose a character due to trade with another player"
- http://vocab.linkeddata.es/vgo/#purchasesGameOffering and GameProduct: "Basically a Game Product can be anything, a character, an item or an achievement." but has no domain specified... 

## References

- [[ar.an-ontology-for-videogame-interoperability]]