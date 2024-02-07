---
id: ntvb3az1j4ssjfzgfd39m88
title: Delta Snapshots
desc: ''
updated: 1707282935772
created: 1707282935772
---

- "messages that are custom-tailored to each player"
- "If deltas are absolute, there is no need for clients to store past states. The server can calculate the delta from the last acknowledged state"

## Process

- first snapshot is the Gamestate in its entirety
- each snapshot has a sequence number. If the client receives a snapshot that has an older sequence number than the last received, it is discarded,
- When the client receives a snapshot, it also acknowledges the receipt to the server by sending the sequence number.
- The server now knows what the client knows. It can generate custom-tailored snapshots based on the last acknowledged sequence number, sending the client only the data that has changed. This is what’s called a delta snapshot.

## Caveat

- Snapshots aren’t suitable for all games. They’re great for non-deterministic physics-based games that require frequent synchronization on a limited amount of entities. If you have a fully deterministic game (meaning the same inputs will produce the exact same result each time) such as a fighting game, input rollback systems are a better, more efficient way to go, with no need for positional deltas. If you’re making an RTS with hundreds or thousands of entities, you’ll need a different network model altogether.

## References

- https://medium.com/@geretti/netcode-series-part-2-data-channels-c12e9a238800
  - "Is the data latency important?— Is the data essential to game state?"
  - "Projectile hits, however, are not entities. They don’t spawn, carry changing properties, or despawn. They are discrete events. Snapshots can tell the client that the enemy health was reduced by 30hp, but they can’t inform if it was caused by a single 30hp hit, or 3x10hp hits.
    - thought: 
      - snapshotting < events;
      - clients are going to have to be "dumb" in the sense that they don't have the data/assets built in. almost everything gets computed on the server side
      - 