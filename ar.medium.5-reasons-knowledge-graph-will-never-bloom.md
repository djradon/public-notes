---
id: 16o50hqhvp6czw8zsbo1k92
title: 5 Reasons Knowledge Graph Will Never Bloom
desc: ''
updated: 1721489598454
created: 1721487565037
---

- https://dongshengwang.medium.com/5-reasons-knowledge-graph-will-never-bloom-418601957f33
- topics: [[t.cs.semantic-web]]

## thoughts

- logical and gramatical problems abound, but kernels of truth...

## Four Reasons SW has faded

### RDF Sharing disability

- "Academic agents have been mainly focused on building their knowledge bases, which are intended to be global datasets. However, these RDF databases often suffer from being hard to understand, outdated, unreliable, and substantially diverse, making it challenging to achieve linked data. As a result, they tend to become another type of local databases."
- "industrial agents are more realistic and pragmatic, and there is currently no strong incentive for them to widely and effectively transform or share their data as RDF."
  - Many companies display data on the internet in JSON format, which is often sufficient for developers. 
  - Even if some private companies and industries are willing to share their data, they may not want to make the additional effort to publish RDF data since it requires more effort than reward.

### Expensive to consume RDF

- When working with RDF data, it is necessary to first study its schema and parse it into local memory to assemble triples into complete instances. This process is necessary because triples of the same entity can be distributed, and predicates can be arbitrary.
- Without adopting external RDFs effectively, a local RDF database is not superior to a simple relational database.

### Ontology definition splurging

- too many custom ontologies
  - t.2024.07.20.08 meh, kinda saying "too many data models" 
- understanding a new RDF dataset from an unknown source can take a significant amount of time
  - t.2024.07.20.08 unavoidable to a degree, but good naming helps

### Expensive to use first-order logic

- inference accuracy remains unsatisfactory and unreliable
  - first-order logics have not been widely adopted in traditional AI systems, and their reasoning efficiency and effectiveness are questionable.
  - descriptive logics require high-quality and small-scale data, making it infeasible to scale up to the large amounts of dirty data generated daily.
  - alternative methodologies such as machine learning models trained on massive datasets can be more effective and efficient than descriptive logics. As a result, first-order logics are expensive and replaceable.

## Five reasons KG will not be thriving

### Entities are hard to be generalized

- I think he means/includes classes?
- granularity and ambiguity

### Relation splurging and explosion

- relations can become exponentially complex, derived from the simple triple format. To express the natural relations between entities, the knowledge graph often uses compound phrases. However, facing hundreds of relations like song_of, written_by, create_by, is_author_of, build_time, cause_by, has_been_to, and has_visited, humans can become confused by the ambiguity, let alone machines. This is why it is sometimes necessary to define the domain and range if you expect certain relations to belong to specific classes. Consumers must first understand the concept and relation definition of the KG. However, as relations grow from different sources, they become increasingly ambiguous with one another, such as belongs_to, part_of, and included_by.

### Simple triple format leads to higher complexity

- the KG creator, in turn, has to define complex relations with the compound phrase for accurate description
- "We should not blame that developers sometimes question would it be more straightforward if we can design a relational database table. When you employ a relational database with a table name called ‘president’, you can easily define the properties that belong only to this table like name, x_th, period, spouse, spouse_period, etc. And this concept oriented design, in general, is more accessible and human-understandable than RDF oriented design."

### Hard to access Knowledge Graph as a database

- SPARQL is complicated, 
- triples can be located in different lines or different files and databases.
- triples are usually not readable due to URIs

### Unreliable quality and generation latency

## Why people still insist it

- KG is currently the most promising technology that shares similarities with human thinking.
- There are no other alternative technologies that can sustain hope for the next breakthrough, especially after the advancements of deep learning from the connectionism community.
- We acknowledge that there is a compromise between symbolism researchers and connectionism researchers.
- Technology media often prioritize propaganda over accountability, and researchers may not face consequences for making grandiose claims.

## Suggestions

- Technically, there is a need to strike a balance between the simplicity of triple formats and the information richness of n-tuple structures in representing knowledge. While technologies like Neo4j are moving in this direction, there is a need for a new standard that involves researchers and developers in defining a schema and n-tuple knowledge that can be easily understood and accessed by both humans and machines.
- While URI is considered a vital requirement for ensuring global uniqueness, cheaper alternatives could be used instead. For example, universally unique identifier (UUID) is a widely known identifier that can be used to identify entities both locally and globally. UUIDs can ensure that entities from different datasets remain globally unique even when merged. Thus, we can use UUIDs to replace URIs for identifying entities and predicates with little impact.


## Comments

- In my career, I've transitioned from Knowledge Graph to Entity Component System - an  [[t.cs.entity-component-system]]can be quickly implemented using existing scalable, robust data technologies (e.g. RDBMS), and components/attributes represented as vectors/columns and matrices/dataframes/tables are more useful in data analysis/science (and other software) contexts.
- Your analysis makes some points in favor of SQL ontologies and semantic SQL: https://timbr.ai/blog/replacing-relational-sql-with-semantic-sql/