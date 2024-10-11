---
id: o5wcm13hu85h1xj1eg96hkr
title: 'getting kosmion off the ground'
desc: ''
updated: 1728668577472
created: 1728645571538
---

## Back on the subject of using named graphs for each relator. I guess you can say things about named graphs with RDF statements, but there must be some downsides. What are the benefits?

Using **named graphs** for each **relator** in your ontology can offer several **benefits** and **downsides** that are worth considering.

### Benefits of Using Named Graphs for Relators:

1. **Contextualization**:
   - Named graphs allow you to **group** RDF triples and associate them with a **context**. In your relator-based approach, each named graph could represent a specific **relator** (or relationship), meaning you can group all the triples relevant to that relator together. This makes it easier to manage and query relationships as distinct units.
   - Example: You could store all the facts about a specific collaboration (like participants, roles, and start dates) in one named graph.

2. **Statements About Statements**:
   - RDF reification allows you to make statements **about** statements (such as who asserted them or when they were asserted), but this can be verbose. Named graphs provide a **more efficient way** to achieve this by letting you attach metadata to the entire group of triples (the graph) rather than reifying each individual statement.
   - You can add metadata like:
     - Who created the relator.
     - The **validity period** of the relator's relationship.
     - Provenance information (e.g., **who asserted** the relator's facts and when).

3. **Managing Temporal Information**:
   - Named graphs align well with your goal of managing **bitemporality**. For each relator, you can use named graphs to track **valid-time** and **system-time** for a group of relationships, making it easier to handle historical data.
   - You could attach temporal metadata to a graph, allowing you to **invalidate** the graph (e.g., by adding a `:system-to` property), rather than modifying individual triples, preserving immutability.

4. **Granular Access Control**:
   - Named graphs allow for **fine-grained access control**. In systems where you need to control who can read or modify specific relationships or parts of the data, named graphs can be used to restrict or permit access to different users or agents based on the graph.
   - This can be useful for **multi-tenant systems** where different users should have access to different parts of the RDF dataset.

5. **Simplifying Queries**:
   - By using named graphs, you can **simplify complex SPARQL queries** by targeting a specific graph rather than filtering out irrelevant triples from the entire dataset. This leads to more efficient and focused queries, particularly when dealing with large datasets.
   - Example: `GRAPH ?g { ?s ?p ?o }` allows you to query only within a specific named graph `?g` rather than over the entire dataset.

### Downsides of Using Named Graphs for Relators:

1. **Increased Complexity**:
   - Managing large numbers of named graphs can introduce **complexity** into your system. If every relator has its own named graph, you might end up with a proliferation of graphs, making it harder to manage, query, and maintain consistency across the dataset.
   - Query complexity could increase, as you'll need to frequently reference the correct graph in your queries.

2. **Compatibility with Tools**:
   - Not all RDF tools or triple stores offer full support for **named graphs**. While many SPARQL-compliant systems (like **Apache Jena** or **Blazegraph**) support named graphs, some reasoners or data storage systems might not fully leverage named graph semantics, leading to limitations in performance or capability.
   - Named graphs are often seen as **orthogonal** to reasoning capabilities, so if reasoning across graphs is needed, it may be more complex to implement.

3. **Loss of Granularity for Statements**:
   - Named graphs are a good way to make statements about **groups of triples** but don’t work well for making statements about **individual triples**. If you need to add metadata to specific statements (for instance, to one triple in a relationship), you may still need to rely on **reification** or another mechanism.

4. **Performance Overhead**:
   - In some triple stores, using a large number of named graphs can add **performance overhead**, as each named graph is managed separately. Querying across multiple graphs or keeping track of dependencies between them can increase **query execution time** and **memory consumption**.

### Summary:

#### **Benefits**:
- **Contextualization**: Grouping relationships in a relator-based model.
- **Statements about statements**: More efficient than reification.
- **Temporal management**: Simplifies tracking system and valid time.
- **Granular access control**: Easier security management per relator.
- **Simplified querying**: Targeting specific graphs for more focused queries.

#### **Downsides**:
- **Increased complexity**: Managing many named graphs can be cumbersome.
- **Tool compatibility**: Some RDF tools may not fully support named graphs.
- **Lack of granularity**: Cannot make statements about individual triples easily.
- **Performance concerns**: Can cause overhead in some systems.

Incorporating **named graphs** into your **Kosmion** ontology could be beneficial, especially for managing temporal and relational information in a structured way. Just consider the potential for complexity and tool compatibility when scaling your system.

## I think querying might be too tricky with named graphs. Let's try to define kosmion without them for now.

Got it! Let's focus on defining **Kosmion** without relying on named graphs.

Since **Kosmion** involves **relators**, **immutability**, and **bitemporality**, we can still manage all of these elements directly within RDF using standard mechanisms like **triples**, **custom properties**, and **temporal fields** while ensuring the model remains simple to query.

### Key Aspects of Kosmion (without Named Graphs):

#### 1. **Relators as Central Entities**:
   In Kosmion, **relators** are still the core units for representing relationships between entities. Each relator will be treated as a first-class entity with its own set of properties and relationships. However, instead of grouping these into named graphs, we'll focus on representing them directly within the RDF structure.

   Example:
   ```turtle
   :Relator1 a :Relator ;
             :role1 :Person1 ;
             :role2 :Person2 ;
             :relationshipType :Friendship ;
             :validFrom "2023-01-01T00:00:00" ;
             :validTo "2024-01-01T00:00:00" ;
             :system-from "2023-01-01T10:00:00" ;
             :system-to "9999-12-31T23:59:59" .
   ```

#### 2. **Immutability with System-Time**:
   Each relator instance is immutable, meaning that once it is created, it cannot be modified. To support immutability, we'll introduce **system-time properties** (`:system-from` and `:system-to`) to record when a relator was valid in the system, as discussed earlier.

   If a relator needs to be "invalidated," a new version of the relator is created, and the `:system-to` field on the old version is updated to mark when it was replaced.

   Example of invalidating a relator:
   ```turtle
   :Relator1 a :Relator ;
             :role1 :Person1 ;
             :role2 :Person2 ;
             :relationshipType :Friendship ;
             :validFrom "2023-01-01T00:00:00" ;
             :validTo "2024-01-01T00:00:00" ;
             :system-from "2023-01-01T10:00:00" ;
             :system-to "2023-06-01T12:00:00" .  # Invalidated

   :Relator2 a :Relator ;
             :role1 :Person1 ;
             :role2 :Person2 ;
             :relationshipType :Friendship ;
             :validFrom "2023-01-01T00:00:00" ;
             :validTo "2025-01-01T00:00:00" ;
             :system-from "2023-06-01T12:00:01" ;
             :system-to "9999-12-31T23:59:59" .
   ```

#### 3. **Bitemporality**:
   By combining **valid-time** (the time when a relationship is true in the real world) and **system-time** (the time when the information was inserted or updated in the system), you achieve **bitemporality**. These timestamps will be properties on each relator instance, and querying will involve filtering based on these properties.

   Bitemporal queries would use both the **validFrom/validTo** fields and the **system-from/system-to** fields to reconstruct data at any point in the past, both in terms of its real-world applicability and system-level existence.

#### 4. **Querying Without Named Graphs**:
   You can still structure your **SPARQL queries** to filter for relators and their roles using the **system-time** and **valid-time** fields. Here's an example of a query to retrieve valid relators for a specific time period:

   ```sparql
   SELECT ?relator ?role1 ?role2
   WHERE {
     ?relator a :Relator ;
              :role1 ?role1 ;
              :role2 ?role2 ;
              :validFrom ?vf ;
              :validTo ?vt ;
              :system-from ?sf ;
              :system-to ?st .
     FILTER (?vf <= "2023-07-01T00:00:00"^^xsd:dateTime && ?vt >= "2023-07-01T00:00:00"^^xsd:dateTime) .
     FILTER (?sf <= "2023-07-01T00:00:00"^^xsd:dateTime && ?st > "2023-07-01T00:00:00"^^xsd:dateTime) .
   }
   ```

   This query retrieves relators that were valid both in real-world time and in system time as of July 1, 2023.

### Conclusion:
By eliminating named graphs, we simplify the querying process, but still maintain the **relator-based** structure and **bitemporal data handling** through direct RDF properties. This keeps the model straightforward while still enabling powerful temporal reasoning.

## I was thinking instead of "system-from" and "system-to", maybe use "genesis" and "tombstone" or maybe "relator-genesis" and "relator-tombstone". What do you think?

Using **"genesis"** and **"tombstone"** (or the more specific **"relator-genesis"** and **"relator-tombstone"**) instead of **"system-from"** and **"system-to"** could work well for your approach, especially since these terms can evoke the **lifecycle** of a relator in a more **semantic** and **contextualized** way.

### Pros of "Genesis" and "Tombstone":
1. **More Intuitive Meaning**: 
   - **"Genesis"** naturally suggests the **beginning** or **creation** of something, making it a clear, human-readable way to indicate when a relator was first created or became valid in the system.
   - **"Tombstone"** effectively conveys the **end** or **termination** of something, hinting that the relator has been "retired" or invalidated without deleting the record. The term "tombstone" is also commonly used in databases and versioning systems to represent records that are no longer active but still kept for historical reference.

2. **Relational Context**:
   - Using **"relator-genesis"** and **"relator-tombstone"** adds specificity, clearly indicating that these fields pertain to the **lifecycle of relators**. This helps maintain clarity in a complex model and avoids any potential confusion about whether these properties apply to the entire entity or just to the relationship.
   
3. **Aligns with Bitemporality**:
   - These terms can still fit into your **bitemporal model**—they essentially function as **transaction-time markers** (system-time) while offering more understandable labels, which is particularly useful when working with ontologies or datasets meant for human interpretation.

### Things to Consider:
1. **Semantics and Interpretation**:
   - While **"genesis"** and **"tombstone"** are intuitive, they could be interpreted as more symbolic than **"system-from"** and **"system-to"**. However, if your goal is to emphasize the lifecycle of **relators** rather than using a strictly technical nomenclature, these terms might be preferable.

2. **Consistency in Queries**:
   - Ensure that your terms are consistently used across the ontology. For example, if you use "genesis" and "tombstone," they should be applied in contexts where relator lifecycles are being tracked, so that users querying the system know exactly what each term refers to. 

3. **Documentation and Usability**:
   - Since **"genesis"** and **"tombstone"** are not typical RDF or temporal database terms, good **documentation** will be necessary to clarify the meaning of these properties for users unfamiliar with the terminology.

### Example:
```turtle
:Relator1 a :Relator ;
          :role1 :Person1 ;
          :role2 :Person2 ;
          :relationshipType :Friendship ;
          :validFrom "2023-01-01T00:00:00" ;
          :validTo "2024-01-01T00:00:00" ;
          :relator-genesis "2023-01-01T10:00:00" ;
          :relator-tombstone "9999-12-31T23:59:59" .  # Still valid
```

### Summary:
Using **"genesis"** and **"tombstone"** (or their more specific forms **"relator-genesis"** and **"relator-tombstone"**) could give your ontology a **clearer**, more **intuitive** way to express the lifecycle of relators, making it more approachable and human-readable while still aligning with the requirements for immutability and bitemporality. If the terms resonate with the overall semantics of your model, they seem like a good choice.

## should class membership for a-box individuals, usually handled by "rdf:Type", be handled with a relator? Or both? I'm leaning towards just using a "type-relator" superclass, with specializations corresponding to the OntoUML class stereotypes.

Your idea of using a **"type-relator" superclass** to handle **class membership** for A-box individuals, instead of the typical `rdf:type`, makes sense in the context of your **relator-based** approach and the specific semantics you're trying to capture. Here's why this could be a compelling approach, along with some considerations for deciding between relators and `rdf:type`:

### Why Use a "Type-Relator" Superclass:

1. **Consistency with Relator-Based Approach**:
   - If your goal is to treat **relators** as central to the ontology and to capture relationships as **first-class entities**, using a **type-relator** to represent **class membership** maintains consistency. Instead of relying on the direct `rdf:type` relation, you're treating the membership as a **relationship** with its own context and attributes.
   - This approach allows you to enrich the **class membership** with additional metadata (such as **time**, **creator**, or **source**), which would be difficult to capture using `rdf:type` alone.

2. **Specialization with OntoUML Stereotypes**:
   - The use of specializations for different **OntoUML stereotypes** (e.g., **kind**, **role**, **collective**) allows you to add **semantic richness** to your model, reflecting the different **types of class membership** or the nature of the relationship between the individual and the class. This is particularly valuable if you want to model **contextual or dynamic membership** (e.g., someone’s role changing over time).

3. **Flexibility for Evolving Membership**:
   - Using a relator for class membership can support **dynamic or conditional class membership** that might change over time or in different contexts. For example, an entity could be linked to a class via a **type-relator** for a certain period (temporal validity) or under certain conditions, without altering the original entity’s definition. This would allow you to represent the **temporality** of class membership.

4. **Extending the Membership Concept**:
   - A type-relator would allow you to handle more complex **multi-class membership** cases, where an individual may belong to multiple classes under different contexts or with varying roles. Each membership could have its own relator, allowing for a clear and structured representation of **multi-class** individuals.

### Challenges with Replacing `rdf:type`:
1. **Efficiency**:
   - RDF's built-in `rdf:type` is optimized for **stating class membership** and is natively supported by RDF triple stores and reasoners. Moving to a relator-based model for class membership could increase **query complexity** and **storage overhead**, as every membership would involve additional triples to describe the relationship.
   
2. **Compatibility with Tools and Reasoners**:
   - Many RDF tools, reasoners, and ontologies expect class membership to be represented via `rdf:type`. Moving to a custom relator-based approach could reduce compatibility with existing RDF tooling, requiring custom logic for inferencing, querying, and reasoning over class memberships.

### Middle Ground (Both Approaches):
Another possible option is to **combine both approaches**. You could keep `rdf:type` for **basic class membership** where appropriate (especially when there's no need for additional metadata), and introduce the **type-relator** for cases where **metadata** or **temporal aspects** are necessary.

### Example:
Using a **type-relator** to represent the class membership of an individual in a specific context:

```turtle
:Person1 a :Person .

:TypeRelator1 a :TypeRelator ;
              :subject :Person1 ;
              :class :Employee ;
              :relator-genesis "2023-01-01T00:00:00" ;
              :relator-tombstone "2023-12-31T23:59:59" ;
              :role :FullTimeRole .
```

This expresses that **Person1** is an **Employee** via a relator relationship with temporal and contextual attributes.

### Conclusion:
Your inclination to use a **"type-relator" superclass** for handling class membership is a natural fit for your **relator-based ontology**, especially if you're focused on capturing richer metadata, temporal aspects, and contextual class membership. While this approach offers greater **flexibility and expressivity**, it might come at the cost of **efficiency** and **compatibility** with existing tools, so using a hybrid model that also supports `rdf:type` where possible could strike a good balance.

## I'm thinking we should try to only use type-relator for data, but rdf:type can be used for metadata. That could keep relators about relators from spiraling out of control.

Your approach of using **rdf:type** for **metadata** while using **type-relators** strictly for **data** makes a lot of sense, especially in terms of keeping the ontology manageable. This separation can help prevent the complexity of relators referencing other relators, which could lead to spiraling structures and potentially hard-to-manage RDF graphs.

### Key Advantages of This Approach:

1. **Simplifies Metadata Management**:
   - Using `rdf:type` for **metadata** keeps things simple when assigning metadata properties like `relator-creator`, `relator-genesis`, and `relator-tombstone`. This allows for a straightforward representation without needing additional layers of relators just for metadata.
   
2. **Prevents Recursive Complexity**:
   - Without needing to use relators to describe the **metadata of other relators**, you prevent the complexity that would come from having relators refer to other relators. This ensures that the structure of the ontology remains clear, and querying or reasoning over the data doesn’t become overly complicated.

3. **Optimized for RDF Tools**:
   - Since most RDF systems are optimized for handling `rdf:type` and metadata properties like **provenance** (e.g., `dc:creator`, `prov:wasGeneratedBy`), this hybrid approach ensures that your ontology remains compatible with existing **reasoners** and **tools** without adding additional query complexity.

### Example Use Case:

For the **data layer**:

```turtle
:Person1 a :Person .

:TypeRelator1 a :TypeRelator ;
              :subject :Person1 ;
              :class :Employee ;
              :relator-genesis "2023-01-01T00:00:00" ;
              :relator-tombstone "9999-12-31T23:59:59" .
```

For **metadata**:

```turtle
:Relator1 a :TypeRelator ;
          rdf:type :MetadataRelator ;
          :relator-creator :UserX ;
          :relator-genesis "2023-01-01T00:00:00" ;
          :relator-tombstone "2023-12-31T23:59:59" .
```

### Benefits:
- **Efficiency**: Keeping `rdf:type` for metadata ensures that reasoners and tools can handle the ontology efficiently, without requiring them to resolve complex, relator-based references.
- **Scalability**: By limiting the use of **type-relators** to only data relationships, you reduce the risk of excessive nesting, which helps ensure the scalability of your system as it grows.
- **Consistency**: The clear distinction between **data** and **metadata** ensures that you maintain consistency throughout the ontology, making it easier to manage and extend in the future.

In short, this approach strikes a good balance between **expressivity** and **simplicity**, keeping your ontology well-structured and scalable.

## For your first example, we wouldn't include ":Person1 a :Person ." because that is data.

Thanks for the clarification! You're right—`":Person1 a :Person ."` would fall under **data**, so it would be managed by a **type-relator** and not explicitly stated with `rdf:type` in this approach.

Here's the corrected example:

### For **data layer** (using **type-relator**):

```turtle
:TypeRelator1 a :TypeRelator ;
              :subject :Person1 ;
              :class :Employee ;
              :relator-genesis "2023-01-01T00:00:00" ;
              :relator-tombstone "9999-12-31T23:59:59" .
```

### For **metadata** (using **rdf:type**):

```turtle
:TypeRelator1 rdf:type :MetadataRelator ;
              :relator-creator :UserX ;
              :relator-genesis "2023-01-01T00:00:00" ;
              :relator-tombstone "2023-12-31T23:59:59" .
```

In this structure:
- **Type-relator** handles data-level class membership (`:class :Employee`) without involving `rdf:type`.
- **rdf:type** is reserved for describing the metadata about relators (such as their creation and tombstone information) without complicating the data itself.

This clear separation of concerns will help keep your model concise, scalable, and easy to query.

## Remind me, is it true annotations can't have IRIs as the object?

Yes, it is true that **OWL annotation properties** (which are used for metadata or comments about classes, properties, and individuals) typically **cannot have IRIs (Internationalized Resource Identifiers) as objects** under certain conditions, depending on the version of OWL and the context. However, this restriction can vary slightly based on the specific tools and reasoning capabilities you are using.

### OWL 2 and Annotations:
In **OWL 2**, annotations are more flexible, but by default, **annotation values** are expected to be **literals** (e.g., strings or datatypes). However, **IRIs can be used as annotation values** under some conditions, though reasoners may not always support inference over annotations where an IRI is the object.

For example:
```turtle
:Person a owl:Class ;
        rdfs:label "Person" ;
        rdfs:seeAlso <http://example.org/someDocument> .
```
In this case, the `rdfs:seeAlso` annotation property can have an IRI as its object, and this is legal in OWL 2. The annotation is still not part of the core logical inference process (meaning it doesn’t affect entailments), but the IRI is valid as an annotation object.

### Tool and Reasoner Limitations:
Some reasoners might not fully support IRIs as objects in annotations or might treat them as non-logical metadata that doesn’t influence reasoning outcomes. Depending on the tools you use (like **Protege**, **HermiT**, or **Pellet**), support for this might vary in terms of how they handle or interpret such annotations.

### Summary:
- **IRIs** can be used as annotation objects in **OWL 2**.
- The reasoning and inference processes typically ignore annotations, meaning that while IRIs are technically allowed, they won’t participate in logical entailments.
- It's important to check if your specific RDF or OWL tools fully support this usage depending on the version of OWL and the reasoning you need.

Let me know if you'd like more details on how different tools handle this or any follow-up questions!

## I'm worried about "A «Relator» must mediate at least two distinct individuals." from the OntoUML docs. Why couldn't a relator apply to unary relationships, i.e., no mediation, just ???

The requirement from **OntoUML** that "A «Relator» must mediate at least two distinct individuals" is intended to align with the **ontological commitment** that relators represent **connections** or **dependencies** between entities. This is a foundational idea in **ontological modeling** where relationships are typically modeled between multiple distinct entities to represent some form of interaction, shared activity, or association.

However, in your **Kosmion ontology**, you may wish to represent **unary relationships**—situations where a relator applies to a single individual or even describes something **internal** to that entity. Here are a few reasons why this could make sense:

### Why a Relator Could Apply to Unary Relationships:

1. **Self-Referential States**:
   - An entity may have internal states, conditions, or **attributes** that do not directly involve other entities. For example, an individual's **status**, such as being "in a reflective state" or "meditating," could be seen as a relationship between the entity and itself or its own internal context.

2. **Complexity of Real-World Scenarios**:
   - In many real-world applications, an entity might have a context-specific **role** or status that doesn't require interaction with another entity. For instance, the **context** of being "self-employed" may not directly imply another individual, but it is still meaningful to model as a relational state.

3. **Expressivity in Modeling**:
   - The **expressivity** you are aiming for, especially in **OWL Full**, blurs the line between instances and classes (A-box and T-box), and allows you to be more flexible with how you model **roles** and **relations**. Allowing unary relationships gives you greater flexibility in capturing **complex** scenarios without forcing the introduction of additional entities unnecessarily.

### Possible Implementation Approaches:

1. **Relaxing the Mediation Constraint**:
   - You can **relax** the mediation constraint for your **relator** class to allow for the possibility of **unary** relationships. This could mean allowing relators to have a minimum cardinality of **one** (instead of two) on their mediated roles.

2. **Contexts as Unary Relators**:
   - You have already introduced the concept of **context** in your ontology. It could be useful to allow **contexts** to also be represented as a type of **relator** that applies to a single entity, specifying the **applicable reality** without requiring mediation between two distinct entities.

### Example Revision in Kosmion Ontology:

To support unary relationships, you could revise the **SHACL constraints** for the relator to allow **at least one** mediated role, rather than **at least two**. You could also add a property for **mediates** that allows for a **single entity** to be referenced.

Here is how you might modify the SHACL constraints for the **relator** class:

```turtle
kosm:relator-shape a sh:NodeShape ;
    sh:targetClass kosm:relator ;
    sh:property [
        sh:path kosm:relator-genesis ;
        sh:minCount 1 ;
        sh:maxCount 1 ;
        sh:datatype xsd:dateTimeStamp
    ] ;
    sh:property [
        sh:path kosm:relator-tombstone ;
        sh:maxCount 1 ;
        sh:datatype xsd:dateTimeStamp
    ] ;
    sh:property [
        sh:path kosm:mediates ;
        sh:minCount 1 ;
        sh:nodeKind sh:IRI
    ] .
```

In this revision:
- **kosm:mediates** represents the connection between the relator and the mediated entity. By setting `sh:minCount 1`, you allow the relator to mediate **at least one** entity, thereby making **unary relationships** possible.

### Summary:
The OntoUML requirement that a **relator must mediate at least two distinct individuals** serves a specific philosophical and ontological view, but it is not necessarily suitable for all types of modeling. In your case, you could adopt a more **flexible approach** that supports **unary relationships**, especially for self-referential or contextual scenarios. Modifying the **SHACL constraints** as described could help realize this flexibility while retaining the ability to model **binary or higher-order relationships** where needed.


## So , every relator will need at least one "relata". So we need a super-property to use for the relationships described by a relator. gUFO uses "mediates", but maybe something more generic would be appropriate.


I've added a **super-property** called `kosm:relates` to serve as a more **generic** property for capturing entities involved in relationships described by a relator. The **SHACL constraint** has also been updated to enforce that every **relator** must use this property to relate at least one entity.

If you have any other thoughts on the naming or additional properties you'd like to introduce, just let me know!


## Do you think we should add a class "Type" which is sameAs http://purl.org/nemo/gufo#Type, and its subclass RelationshipType, and RelationshipType's subclasses ComparativeRelationshipType and MaterialRelationshipType ?

I've added the **Type** class, linking it to **gUFO's Type** (`gufo:Type`), and introduced **RelationshipType** as a subclass of **Type**, along with its subclasses **ComparativeRelationshipType** and **MaterialRelationshipType**.

This adds more flexibility to your ontology for defining different **types of relationships**, including their specific subtypes. Let me know if you need more refinements or additional classes!