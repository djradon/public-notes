---
id: 9mv0i20dy7qqiqfzxfgvwwn
title: Egeria
desc: 'Open metadata and governance for enterprises - automatically capturing, managing and exchanging metadata between tools and platforms, no matter the vendor.'
updated: 1709451527935
created: 1709279074638
---

- [[c.software.data-discovery]]
- url: https://egeria-project.org/
- built_on: [[prct.xtdb]]

- "Egeria supports an integration of different catalogs through a metadata event bus, but it doesn’t seem to be feature complete yet as of this writing. " t.2020.12.07

## Topics

### Roles vs Personas

- https://egeria-project.org/practices/coco-pharmaceuticals/roles-vs-personas/overview/ 
- ![](/assets/images/2024-03-02-23-34-16.png)
- roles have a context. 
  - For example, Tessa is a manager, but not for everyone in Coco Pharmaceuticals. She is a manager of a specific team. Similarly, she may be a system owner, but not of all systems.
- roles have a scope "and as we design the Egeria software, we need to be sure that this code is included with the definition of the role. We also need to ensure roles can be combined together to form the complete "job" that an individual performs."

### Schema

- "A schema describes the structure of the data associated with an Asset. The technology that supports the asset often limits the structural choices for data. For example:

    A relational database organizes data into collections of tables and columns.
    Technologies such as JSON or XML, organizes data into nested structures.
    Graph databases organizes data in nodes and relationships.

These differences need to be represented in the Open Metadata Types. However, at the same time, data governance is concerned with the accuracy and appropriate use of individual data values. This is very expensive if each data item was governed individually so the data governance practices aim to group like data together, so they can be governed in a consistent way. As such, the open metadata types provide a root set of types that all the specific schema structures inherit from."
- https://egeria-project.org/concepts/schema/


## Examples

- The Egeria community uses the Coco Pharmaceuticals personas to test that there is easy movement from role to role.

This is implemented as follows:

  - Each person has a personal profile (stored as Person entity) that describes the individual (persona).
  - The Egeria community uses the Coco Pharmaceuticals [personas](https://egeria-project.org/practices/personas/overview) to test that there is easy movement from role to role.

This is implemented as follows:

-   Each person has a personal profile [(stored as Person entity)](https://egeria-project.org/types/1/0112-People) that describes the individual (persona).
-   Linked off of the personal profile are person roles [(stored as PersonRole entity](https://egeria-project.org/types/1/0112-Peoplel) that define each role (and their associated scope) that the person performs.

The profile and role are managed primarily by the [Community Profile OMAS](https://egeria-project.org/services/omas/community-profile/overview) and this drives the display on Egeria's user interfaces as well as some aspects of security.
