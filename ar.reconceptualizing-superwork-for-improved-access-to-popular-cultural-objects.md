---
id: 7l727346n6d3eclic9b9wkb
title: Reconceptualizing Superwork for Improved Access to Popular Cultural Objects
desc: ''
updated: 1724356624897
created: 1724348807733
---

- https://cpb-us-e1.wpmucdn.com/sites.uw.edu/dist/2/3760/files/2019/09/Reconceptualizing-Superwork-for-Improved-Access.pdf

- topics: [[t.library-science.superwork]] [[sh.t.multiverse]]

## Highlights

- several researchers such
as Carlyle (1996), Svenonius (2000), Antelman (2004), Smiraglia (2007), Kemp (2008), and Smiraglia et al. (2014) have discussed this concept. Similar or relevant concepts also exist in current bibliographic standards such as [[prdct.frbr]], FRBROO, and BIBFRAME 2.0. 
  - Smiraglia (2007) states that the notion of the superwork describes “the abstract intellectual concept of a given work that is the principle node around which all iterations of that work may be collocated”
  - Antelman (2004) and Kemp (2008) have used the term in the context of overarching super-serials that span across all of the title changes that a serialized work might have undergone during the timeline of its publication
    - Example: Dr. Strange, a work which begins as part of Marvel Comics’ science-fiction/horror anthology Strange Tales (in issue #110), eventually expanding to the point of being the whole of the content of Strange Tales (by issue #169), before being renamed as Dr. Strange (also issue #169)
      -  a superwork in this sense would encompass some of Strange Tales and all of Dr. Strange
-  [[prdct.frbroo]] provides a rich set of tools with which the bibliographic universe can be modelled
   -  e.g. F15 Complex Work
      -  t.2024.08.22.10 now part of [[prdct.pressoo]]
      -  While the term complex work does not evoke the grand scope that a term like superwork does, the definition, scoping notes, and examples provided in the FRBROO document seem to, at first, closely align to the definition of superwork and scope of the examples provided later in this paper
      -  it does not seem as though works that are not intended by the creators to be part of one another... are to be modelled using the complex work entity mode
-  [[prdct.bibframe]] hasDerivative and derivativeOf
properties
- we define superwork as an aggregate entity related by:
  - their origins (i.e., derivative works from some ur-work), or
  - shared characteristics, such as theme, characters and world/universe.

### Properties/Characteristics of Superwork

- hasMember: A Superwork is a kind of aggregate.
  - At the very least they stand in a “hasPart” mereological relationship with the individual works that they are made of. 
  - More specifically, the individual works that make up a superwork stand in a mereonymic relationship with the superwork. 
  - If one models a superwork as the kind of thing that derives its identity from the works that compose it, then this narrower relationship is membership
  -  If one models a superwork as the kind of thing that is constituted of the works that compose it, then this relationship is constitution.
  -  If one believes that the works that compose a superwork are brought together through curatorial intervention, then the relationship is the much narrower gathered-into relationship and superworks are identical to bibliographic collections.
-  includesFormat: A Superwork encompasses multiple works in multiple formats related to one another in a multitude of complex ways
   - t.2024.08.22.11 disagree
   - items in a superwork aggregation are related to one another beyond the curatorial sense of membership or the editorial sense of arrange- ment (i.e., they are not the same as collections or series
 - hasCreator: A Superwork will frequently contain works by several (and sometimes hundreds of) authors.
   - it is possible for a superwork to emerge based on works by a single author
 - hasTheme: A Superwork is aggregated around some theme or group of closely related themes.
   - shared fictional universes
   - brands
   - topics

### Challenges

#### Superworks as (non-)Bibliographic Entities

- Reconceptualizing superwork as an aggregation that primarily reflects something that users believe to be true about the bibliographic universe is a useful goal
- better conceptualized as a kind of super-topic? (as opposed to a bibliographic aggregate)
  - "After all, existing cataloging practices and digital information systems have well-developed senses of topical, genre-based, and agent-based access points"
    - While these access points suffice for querying a catalog system we found that they lacked the essential conceptual substance that differentiates bibliographic aggregations from mere search query results— **conceptual mass**
- An alternative is to represent the superwork entity as an abstract entity to which multiple relevant works belong (akin to FRBR Group 1 entities). A benefit here would be a more straightforward collocation of these works under the superwork entity rather than users having to access the network of works that may be grouped under a shared concept, place, and other elements. 


#### Superworks as Bibliographic Aggregates

- the items in a superwork do not seem to be grouped together through the curatorial process of selection. Therefore, it does not seem to be the case that superworks are the same kind of aggregation as a collection.

#### Specialized Relationships among Superwork Members

##### Conceptualizing Crossover superworks

- the mixed presence of characters from two different superworks in a crossover superwork made it feel unnatural to categorize the crossover superwork under one or the other superworks from which the characters originate.
  - t.2024.08.22.12 should be both... categories does kinda imply exclusive, but probably should be modelled as a mixin (RoleMixin)

## Conclusion

