---
id: 8h6vqvqt1mb629yktcb1eoq
title: UCAN
desc: User Controlled Authorization Networks follow the "capabilities as certificates" model, with extensions for revocation and stateful capabilities.
updated: 1713214220993
created: 1687844632811
---

- url: https://ucan.xyz/
- repo: https://github.com/ucan-wg
- created_by: [[org.fission]]
- [[p.hasImplementation]] 
  - [[prdct.noosphere]]
- description: distributed authorization for offline-first apps and distributed systems


## FAQ

### Is UCAN secure against person-in-the-middle attacks?

UCAN does not have any special protection against person-in-the-middle (PITM) attacks.

Were a PITM attack successfully performed on a UCAN delegation, the proof chain would contain the attacker's DID(s). It is possible to detect this scenario and revoke the relevant UCAN but does require special inspection of the topmost iss field to check if it is the expected DID. Therefore, it is strongly RECOMMENDED to only delegate UCANs to agents that are both trusted and authenticated and over secure channels.

## References

- [[ar.capability-myths-demolished]]