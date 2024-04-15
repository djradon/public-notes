---
id: fa1vqnpp2eze4kmn3htnto2
title: Capability Myths Demolished
desc: ''
updated: 1713147442393
created: 1713144314229
---

- https://srl.cs.jhu.edu/pubs/SRL2003-02.pdf
- topics: [[t.cs.authorization.capability-based]]

## Abstract

We address three common misconceptions about capability-based systems: the Equivalence Myth (access control list systems and capability systems are formally equivalent), the Confinement Myth (capability systems cannot enforce confinement), and the Irrevocability Myth (capability-based access cannot be revoked). The Equivalence Myth obscures the benefits of capabilities as compared to access control lists, while the Confine- ment Myth and the Irrevocability Myth lead people to see problems with capabilities that do not actually exist. 

The prevalence of these myths is due to differing inter- pretations of the capability security model. To clear up the confusion, we examine three different models that have been used to describe capabilities, and define a set of seven security properties that capture the distinctions among them. Our analysis in terms of these properties shows that pure capability systems have significant advantages over access control list systems: capabilities provide much better support for least-privilege operation and for avoiding confused deputy problems.

## Highlights

- Property A: No Designation Without Authority.
- Property B: Dynamic Subject Creation.
  - The loss of subject granularity is a severe limitation on the expressiveness of ACL systems
- Property C: Subject-Aggregated Authority Management.
  - In ACL-based systems, the power to edit authorities is aggregated by resource: the ability to change one permission generally comes together with the ability to edit an entire ACL. In capability systems, the power to edit authorities is aggregated by subject: subjects manipulate authorities in their own C-lists.
- Property D: No Ambient Authority.
- Property E: Composability of Authorities
- Property F: Access-Controlled Delegation Channels
- "authorization is just a form of access"

### The Equivalence Myth

- Properties A, B, and C are differences between the apabilities-as-rows model and the ACLs-as-column that should put to rest the equivalence myth

### The Confinement Myth

- capability systems cannot limit the propagation of authority
- "KeyKOS achieves confinement by a mechanism called factories. Essentially, a factory is a mechanism for creating new instances of protected subsystems."

### The Irrevocability Myth

- In an object-capability system, however, capabilities can be composed in such a way as to provide revocable access. Suppose once again that Alice wants to give Bob access to Carol, but Alice also wants to have the option to revoke this access at some time in the future. To accomplish this, Alice could simply create a pair of forwarders, F and R, connected as shown in Figure 6. Of this pair, we may call F the forwarding facet, and R the revoking facet. Alice would send Bob access to F, and retain R for herself. Any messages sent to F get forwarded through R to Carol, so Bob may use F as if it were Carol. This works as long as inter-object interactions are mediated by messages, and messages are handled generically, so that a reusable mechanism can forward any message.

![](/assets/images/2024-04-14-19-05-48.png)