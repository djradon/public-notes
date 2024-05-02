---
id: u9du3ro2al7vsk6pybvkoh9
title: Noosphere
desc: 'a worldwide decentralized repository for thought, belonging to everybody. A decentralized graph, where you own thoughts, and have agency to move your data between services and apps.'
updated: 1714622571078
created: 1653256852662
---

- https://subconscious.network/
- created_by: [[org.subconscious]]
- repo: https://github.com/subconsciousnetwork/noosphere
- related: 
  - [[prdct.decentralized-identifiers]]
  - [[prdct.cid]]
  - [[t.cs.distributed.hash-table]]
- built-on: [[prdct.libp2p]]

## Description

### Public key infrastructure

When Alice and Bob exchanged contact details in the story above, the exchanged data included public keys (encoded as [[DIDs|prdct.decentralized-identifiers]] that represent their respective notebooks. Bob's public key was then recorded against a pet name in Alice's notebook

### Content Addressing

As Alice updated her notebook to include Bob's name, a snapshot of her entire notebook at its latest state was recorded and condensed down to a short, unique ID: a content ID, or [[prdct.cid]]. Such a snapshot and corresponding CID is recorded for every update to every user's notebook (including Bob's).

Similarly, when Bob updated their animal-notes to include a link to cat-thoughts, a new snapshot of the note was recorded and a CID was computed for it. When Alice viewed the index of links in Bob's notebook, what she actually viewed was a mapping of note slugs to their CIDs.

### Immutable data

Noosphere data is formatted in terms of [[prdct.ipld]] and encoded in a low-overhead binary format called DAG-CBOR. Even though a full snapshot is recorded with every revision, new storage space is only allocated for the delta between any two revisions. This strategy is similar to how Git efficiently stores the delta between any two sequential commits.

A data structure that we call a Memo is used to pair open-ended header fields with a retained historical record of revisions to notebooks and their contents:

### P2P routing and discovery

Every user who publishes to the network does so via a gateway server. The gateway represents the boundary edge of user sovereignty, and also gives the user a reliably available foothold in the Noosphere network. The owner of a notebook is also the owner of the gateway, and third-parties neither have or need direct access to it (even in managed hosting scenarios).

The owner of a notebook enables the gateway to publish the notebook to the network using a [[UCAN|prdct.ucan]]-based authorization scheme. UCANs establish a cryptographic chain of proof that allows anyone to verify in place that the gateway was authorized to perform actions such as signing content on the user's behalf (and without asking the user to share cryptographic keys with the gateway).

When the user updates their notebook, they replicate the revision deltas to the gateway over HTTP (as network availability allows), and also tell the gateway which CID represents the latest version of the notebook. The revision deltas are syndicated to the public network via IPFS. Then, the gateway publishes the latest revision CID to a [[t.cs.distributed.hash-table]] (see: Noosphere Name System) mapping it to the notebook's public key and pairing it with the UCAN proof chain.

## Thoughts

- could use an intermediate state, like local changes to a git repo, before "changes" get recorded. 

## References

- [[ar.substack.subconscious.the-minimal-definition-of-user-agency]]
- https://github.com/subconsciousnetwork/noosphere/blob/main/design/explainer.md
