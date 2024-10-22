---
id: 6lje6bt6zlsyvxhrxl0sqze
title: Kosmion Dev
desc: ''
updated: 1729611020978
created: 1729541288729
---

- interlocutor: chatgpt

## kosmion dev 10/12

It looks like you're requesting a summary or update of the development related to Kosmion as of October 12th. Based on the most recent updates and your relator-based approach, here are some key details from the development of Kosmion up to this point:

1. **Relator-Based Approach**: You’ve settled on using a relator-based structure, where predicates become classes, and specific predicate instances become expressions of those classes. This allows for greater flexibility in modeling relationships, and you’re considering avoiding OWL Full for now while continuing to refine the approach.
   
2. **Immutability & Bitemporality**: You’ve moved towards making Kosmion immutable with bitemporality using both 'system-time' (aka 'transaction-time') and 'valid-time' for temporal modeling. You're exploring the idea of system-time as external metadata that governs immutability, while valid-time is treated as internal data.

3. **Naming and Metadata**: You've been working on a naming convention, leaning towards terms like 'genesis' and 'tombstone' (or 'relator-genesis' and 'relator-tombstone') to represent the birth and death of statements, and preferring 'relator-' as a prefix for metadata. 

4. **Slash-Based IRIs**: You're using slash-based IRIs for the Kosmion ontology, establishing a namespace (`https://kosmion.github.io/ont/v0/`) to structure the ontology.

5. **Metadata vs. Data**: You clarified that metadata will not use relators. For example, class membership like `:Person1 a :Person` would be treated as metadata and not included in the relator framework.

6. **Facets and Aspects**: There’s a developing idea where facets (singular properties) might contribute to aspects (emergent properties), but this is still in the exploratory phase for future discussion.

7. **Versioning Strategy**: You are working on a versioning strategy for handling changes to the ontology, where typo corrections or mistakes would be classified as PATCH changes, adding new data would be MINOR, and changing existing data would be considered a MAJOR update.

8. **Redundant Data**: You are considering duplicating relators from relator datasets into the corresponding entity datasets, favoring redundancy to enable consistency checks and smoother attribute management.

If you're looking for more specific details about progress from that date or an update on particular parts of development, let me know!


## regarding #5, I'm thinking to supplant class membership with facets and/or aspects. The kosmion ontology itself might use class hierarchies, but I'd like it to use relators too if that ends up making sense.


Got it! Replacing class membership with facets and/or aspects could give more flexibility, especially if emergent properties can dynamically represent membership or classification based on context. Using relators for class hierarchies within Kosmion also sounds interesting—it could open up new ways of expressing relationships between classes. If you find that relators streamline this kind of hierarchy without losing semantic clarity, it could unify the modeling approach.

Let me know if you want to dive deeper into any aspect of this transition or explore how relators might fit into class hierarchies.

## How does dolce use relators, aka reified relations.

In DOLCE (Descriptive Ontology for Linguistic and Cognitive Engineering), relators (also known as reified relations) are a key concept used to model complex relationships between entities. Here's how DOLCE approaches relators and reified relations:

### Relators in DOLCE:
A **relator** in DOLCE is an entity that mediates or relates two or more other entities (called "relata"). Instead of using a simple direct relation between two entities (like a binary predicate), DOLCE uses relators to represent more complex situations where additional contextual information or properties about the relationship itself are needed. This is often referred to as **reified relations** because the relationship is treated as a first-class entity (a relator) in the ontology.

### Structure of Relators:
In DOLCE, a relator relates multiple entities by connecting them through **roles**. Each entity involved in the relation plays a specific role. The roles themselves are also explicitly modeled as individuals in the ontology.

- **Relator**: An abstract object that represents the relationship as a first-class entity.
- **Roles**: Define the part that each related entity plays in the relationship. Each role is connected to the relator.
- **Mediated entities (relata)**: The entities that the relator connects through their respective roles.

### Example:
Let’s say we have a **marriage** relationship between two people. In DOLCE:
- The **marriage** would be represented by a relator (i.e., the marriage itself is an entity).
- Each spouse would be connected to the marriage relator by a **role** (e.g., "spouse role").
- The actual individuals (the spouses) are the entities that play these roles.

In this case, the **marriage relator** connects the two individuals through their roles as spouses. This allows for adding more detailed information to the marriage (e.g., start date, location, legal status) that would be difficult to represent with just a direct relation between two individuals.

### Formalization:
In DOLCE, relators are formalized as follows:
- A **relator** is a subtype of **non-physical endurant** (meaning it is something that persists over time but is not physical).
- Relators require at least two **roles** to be associated with them, and each role must be connected to an entity that participates in the relationship.
- A role mediates between the relator and the specific entities.

### Key Concepts in DOLCE:
- **Endurants**: Persistent entities, including physical and non-physical ones.
- **Perdurants**: Events or processes that occur in time (which can also be related via relators).
- **Roles**: Functions or parts played by entities in the context of a relator.

### Why Relators?
Relators in DOLCE enable a more detailed and flexible modeling of relationships:
1. **Contextual Information**: By treating relationships as entities, you can attach information directly to the relationship (e.g., temporal, spatial, or contextual properties).
2. **Higher-order Relations**: Relators can mediate more than two entities, making them useful for complex n-ary relationships.
3. **Explicit Role Representation**: By representing roles explicitly, DOLCE ensures clarity in how entities participate in a relationship.

### Comparison with Kosmion:
In your **Kosmion ontology**, the use of relators seems aligned with DOLCE’s approach, where relators represent relationships between entities via roles. If you consider facets or aspects for class membership, relators could also manage the dynamics of how entities play certain roles, without committing to rigid class structures. If you decide to use relators for class hierarchies, you might model class relationships similarly to how DOLCE handles roles between entities and relators, giving you a way to represent evolving or contextualized classifications.

Would this approach fit with your current direction for Kosmion? Let me know if you want to explore how these ideas might map onto your ontology!


## Yes, I think it fits. One difference we've talked about: Kosmion would use relators even for unary relationships.

Great! That distinction makes sense, especially if you're aiming for a consistent and flexible way to represent all kinds of relationships, including unary ones, with relators. This could give you more power to manage the context and evolution of even simple relationships, treating them with the same depth as more complex ones. 

Let me know if you'd like to explore examples of how Kosmion could handle unary relators, or if you want to work out any specific cases!

## Assuming a file-based repository of RDF data, could every file be considered a dataset?

Yes, in a file-based repository of RDF data, every file can be considered a **dataset** depending on how you want to organize and conceptualize the data.

In RDF terms, a **dataset** generally consists of a collection of **graphs**, which may include a **default graph** and any number of **named graphs**. Here’s how it could map to a file-based system:

### Case 1: Single Graph Per File (Simplest Case)
- **One file = One graph**: If each RDF file contains a single graph (whether a default graph or a named graph), then the file can be treated as a standalone dataset. This is common when dealing with smaller or more isolated datasets.
- **Named Graph**: You could define the graph’s name in the file or, depending on the format, assume that the file implicitly represents the default graph.

### Case 2: Multiple Graphs Per File
- **One file = Multiple graphs**: If a file contains multiple named graphs, this is still aligned with the RDF dataset model. For example, a file could include several named graphs, and this file would represent a single RDF dataset with multiple components.
- **Formats**: In formats like TriG (or N-Quads), which support multiple graphs in one file, this approach is straightforward. The file would act as a container for all the graphs, meaning each file is effectively a dataset.

### Case 3: Dataset as a Conceptual Group
Even if a file contains just a fragment of data, you can treat it as part of a larger conceptual **dataset**. In this case, your repository structure might represent:
- A **collection of datasets**: Multiple files that each represent a part of a larger dataset. Here, files might correspond to different graphs, and the dataset is formed by aggregating these files.

### Considerations:
- **File Naming and Graph Identification**: If each file represents a named graph, you might want a consistent naming convention that reflects the graph name or a metadata header to identify it.
- **Performance**: Treating each file as a dataset makes it easier to manage or update specific segments of the RDF data independently. However, performance considerations may arise depending on the number of files and how the data is queried or accessed.

### Kosmion Context
In Kosmion, if you're using **relators** and possibly adopting **named graphs** for each relator, treating each file as a dataset containing one or more named graphs could fit well. This approach would allow you to:
1. **Isolate relator-based clusters** in separate files.
2. **Version or update individual relators** without needing to modify other parts of the ontology.

This would work especially well if you're aiming for a decentralized and modular file-based structure where each file represents a specific facet of your ontology.

Does this align with how you're thinking of structuring RDF data in Kosmion?

## it does++

- dave: So <dave-richardson> would represent an entity, every entity could reference at least one catalog which could "live" anywhere but <dave-richardson/catalog> would be a good first choice, and be referenced from the catalog dataset, say <dave-richardson/catalog/dist> which might have a Turtle distribution named <dave-richardson/catalog/dist/ttl>. But the entity itself could (and should, if no data catalog is referenced) identify at least one dataset directly that is considered the "current" dataset. So <dave-richardson/datasets/v1> could be the corresponding dataset. The different datasets would primarily be used for versioning or for spreading out data over multiple dataset files (in which case a data catalog should be used). I'm inclined against a dataset per relator. I'm not sure what role the named graphs would play any more if there's a dataset per version. Maybe metadata.

- chatgpt:

It sounds like you've settled on a clean structure for organizing entities and datasets, where catalogs and datasets play distinct roles. I think your approach strikes a good balance between modularity (with catalogs) and versioning (with datasets like `<dave-richardson/datasets/v1>`). This allows flexibility in terms of data distribution while keeping a "current" dataset accessible when necessary.

### Named Graphs and Metadata
Since you're thinking about named graphs potentially being useful for metadata, that could work well for things like:
- **Provenance information**: Tracking where the data came from or who created it.
- **Versioning info**: Storing details about when and how a particular dataset was created or modified.
- **Contextual data**: If you need to add contextual information (e.g., temporal or spatial data) to a dataset, a named graph could isolate that metadata without cluttering the primary data.

If you decide to avoid using named graphs for the data itself and instead focus on datasets per version, using them just for metadata makes sense, keeping the structure straightforward.

Let me know if you want to explore any of these aspects further!


## Default Representations

- dave: I wouldn't say settled. But certainly a possibility. There's probably value in the idea of a "default representation" and "default catalog", where the person with access to the IRI-enclosing namespace has control of default and alternate representations , but can delegate total control (by pointing to someone else's data catalog AND default dataset) or partial control (delegating either one). A default catalog could specify its own default represenetation, so there could effectively be two defaults. But that's okay.

- chatgpt: 

That makes sense, especially with the flexibility of delegating control over the catalog or dataset. Having a **"default representation"** and **"default catalog"** controlled by the namespace owner, while allowing delegation, gives you a powerful mechanism for managing data access and structure. It also opens up the possibility of collaborative or distributed data management without losing control over the core representations.

The potential for two defaults (one for the representation and one for the catalog) doesn’t seem problematic, especially if each serves a distinct purpose. The default catalog could handle the organization of data, while the default representation could specify how the data is accessed or interpreted.

If you're still exploring, this setup offers a lot of flexibility. Let me know if you want to dive deeper into specific delegation scenarios or ways to manage defaults!


## ontology vs semantic data

- dave: can you provide references to papers, articles, blog posts, or social media where people argue that ontology does not imply "semantic data" in general or "knowledge graphs" in general? That the term "ontology" should be reserved for domain concepts, analagous to a schema?

- chatgpt:

There are multiple discussions and arguments that highlight the difference between ontologies and the broader concepts of "semantic data" or "knowledge graphs," where the term "ontology" is often more narrowly defined.

1. **Ontologies as Domain-Specific Models**: Some experts argue that an ontology should primarily be viewed as a structured, domain-specific framework for organizing concepts, more analogous to a schema. This perspective suggests that ontologies provide a controlled vocabulary and relationships specific to a domain, whereas knowledge graphs often involve broader integration of data, including instance-level data, which isn't always tied to an explicit, domain-specific ontology. For example, ontologies like the **Gene Ontology** (GO) are specifically tailored to biological knowledge, focusing on well-defined relationships within that context, distinct from general knowledge graphs that handle diverse or cross-domain data【34†source】【35†source】.

2. **Ontologies vs. Knowledge Graphs**: It is often emphasized that **knowledge graphs** are not synonymous with ontologies. Knowledge graphs may include data representations that don’t leverage full semantic inferencing or may involve vast amounts of instance data (like Google’s Knowledge Graph) without the formal semantics typical of an ontology. Some argue that the **schema** in a knowledge graph can exist without the rich conceptual relationships that define an ontology【33†source】【34†source】.

3. **Schema vs. Ontology**: Ontologies are often described as more flexible and expressive frameworks than rigid schemas, but there are arguments that ontologies should focus solely on domain modeling, similar to a schema, rather than broader tasks like data integration or reasoning across large datasets, which are common use cases for knowledge graphs. In this view, ontologies should serve as a "blueprint" for domain concepts, focusing on classes and relationships, rather than extending into instance data and semantic reasoning that knowledge graphs address【35†source】【36†source】.

In summary, many argue that ontologies should remain more like a **schema**, focused on domain concepts, rather than being conflated with the broader tasks of **semantic data** or **knowledge graphs**, which may encompass much more than what ontologies are intended to model.

