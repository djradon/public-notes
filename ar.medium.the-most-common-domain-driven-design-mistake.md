---
id: 80t37arje5p3l8vezhq3n1z
title: The Most Common Domain Driven Design Mistake
desc: ''
updated: 1712898637674
created: 1712898368519
---

- https://medium.com/navalia/the-most-common-domain-driven-design-mistake-6c3f90e0ec2b

## Highlights

- A “Bounded Context” is an area of the business where certain processes and rules apply. It’s where the Central Concept shows up repeatedly under different set of rules that make sense for each Bounded Context, such as:

    Account in banking looks different to Loan Origination vs. Billing vs. Debt Collections vs. Marketing & Communications.
    Policy in Insurance looks different to Underwriting vs. Claims vs. Inspections.
    Product in Supply Chain Management looks different to Planning vs. Sourcing vs. Inventory Management vs. Delivery.
    Reservation in Airlines looks different to Booking vs. Operations vs. Cargo Management vs. Loyalty.
    Order in eCommerce looks different to Purchasing vs. Supply Chain vs. Fulfillment vs. Customer Support.
    Customer in eCommerce looks different to Advertising vs. Ordering vs. Shipping.
- claiming a single view of Accounts goes against the core principles of DDD as it results in an inflexible, bloated Domain Model.

### Unnecessary Coupling

The first is that the Accounts Bounded Context becomes a ‘God Domain,’ taking on more responsibility than it should. As a result, this creates tight coupling with other Bounded Contexts.

### Decomposition

Here is an example of how we may decompose Accounts into Aggregates within different Bounded Contexts:

![](/assets/images/2024-04-11-22-09-12.png)


## Comments

- "The majority of REST examples tend to be concept oriented, and basically just expose the database as things. This leads to incredibly chatty protocols, and all sorts of problems. When you design the bounded contexts and (REST) APIs around processes it becomes much better. But you also need to toss in CQRS and events to communicate changes between these bounded contexts."