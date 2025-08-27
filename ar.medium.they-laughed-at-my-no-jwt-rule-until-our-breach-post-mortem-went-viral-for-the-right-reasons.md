---
id: 43j494yy85o3lwcc4to5647
title: >-
  They Laughed at My No JWT Rule until Our Breach Post Mortem Went Viral for the
  Right Reasons
desc: ''
updated: 1755789539908
created: 1755789494207
---

- https://medium.com/c-sharp-programming/they-laughed-at-my-no-jwt-rule-until-our-breach-post-mortem-went-viral-for-the-right-reasons-3e427244463a

## Summary

Key Tools We Used

    SPIRE/SPIFFE for issuing and rotating workload certs
    Envoy for terminating mTLS at the edge with SDS
    Wireshark for incident packet analysis
    .NET 8 Certificate Authentication Middleware for service-side validation
    HashiCorp Vault for initial CA bootstrapping (later replaced by in-house HSM integration)

Lessons We Learned

    The best security is silent. No alert is often a good thing — when the bad actor gets no response.
    Rotate early, rotate often. Cert rotation sounds scary until you automate it — and then it’s your best friend.
    Trust boundaries should be enforced at the network level, not just the code level.
    If your service doesn’t need to parse auth headers, don’t make it. Let the cert do the talking.