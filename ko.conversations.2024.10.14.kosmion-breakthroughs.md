---
id: 6o2ro0d13fklfyvjtcd4da4
title: Kosmion Breakthroughs
desc: ''
updated: 1729008604578
created: 1728967176412
---

## Properties that specify restrictive domain and range... what's the point? It forces people to buy into your class hierarchy. Re-usable properties should have minimal domain restrictions. Datatype properties can understandably have range restrictions, but object properties should have minimal range restrictions too. Show me counter-examples.

You raise a very good point. **Properties with restrictive domain and range** can limit the **reusability** of those properties across different class hierarchies. Reusable properties should ideally have **minimal or no domain and range restrictions**, particularly if the intent is to encourage broader usage and adoption across ontologies.

### When Restrictive Domain and Range Are Problematic:
1. **Forced Class Hierarchy Adoption**:
   - Properties with restrictive domains and ranges force users to adopt your specific **class structure**. If you want to apply those properties in different contexts that don't match the domain or range exactly, you either have to subclass from the defined hierarchy or avoid using the property, both of which can be cumbersome.
  
2. **Limits to Reusability**:
   - **Domain restrictions** require that any subject of a property belongs to a specific class, making it less reusable across different entities.
   - **Range restrictions** require that any object of the property must belong to a specific class, limiting the types of relationships that can be expressed.

### Examples Where Restrictive Domain and Range Are Reasonable:
- **Datatype Properties with Range Restrictions**:
  - For datatype properties, setting a **range** restriction like `xsd:string` or `xsd:dateTime` can be useful to enforce data **consistency**.
  - Example: A property like `foaf:age` has a range of `xsd:integer` to ensure age values are always represented consistently.

### Examples Where Domain/Range Restrictions Are Problematic:
1. **FOAF Example**:
   - **`foaf:knows`**: This property has a domain of **`foaf:Person`** and a range of **`foaf:Person`**. This means:
     - You can only say that a **person** knows another **person**.
     - You cannot use `foaf:knows` to relate any other type of entities, even though it might be conceptually reasonable (e.g., a **Syngent** knowing a person).
  
2. **Schema.org Example**:
   - **`schema:parent`**: Has a restrictive domain and range that assumes only people can have parents, but there could be scenarios in a fantasy world where a **character** has a non-human parent. Restricting `schema:parent` to only `schema:Person` would limit how this property could be applied in more complex ontologies.

### Counter-Example: Using Minimal Restrictions
- **RDFS Properties**:
  - **`rdfs:label`** and **`rdfs:seeAlso`** are examples of **minimally restricted properties**:
    - **`rdfs:label`** can be used with any subject, with no domain specified, allowing it to be used in virtually any context where a human-readable label is needed.
    - **`rdfs:seeAlso`** also has no domain, allowing it to be used to provide additional references for any kind of RDF resource.

### Considerations for Your Use Case in Kosmion:
- To **maximize reusability**:
  - Avoid specifying strict **domain** and **range** for properties, especially for **object properties**.
  - Only enforce **datatype range** when consistency is crucial, such as for numerical or date values.
- For example, if you want a **relator property** that links any two entities, defining it without a specific domain and range will make it far more reusable across different classes and hierarchies.

### Conclusion:
- **Restrictive domain and range** can make an ontology more **rigid** and less reusable, often forcing users to buy into a specific class structure.
- For **reusable properties**, keeping **domain and range minimal** allows for broader applicability and more **flexible integration** across ontologies.
  
Would you like to adjust any of the properties in your current ontology draft to make them more reusable by removing restrictive domains or ranges?


## To make immutable RDF feasible, there's going to have to be some indirection between an IRI and what you might call a "relator series" or a "relator succession", i.e., a set of micro-datasets that, when an update needs to be made, a new micro-dataset gets created with the latest data and no tombstone, the previous "latest dataset" get a tombstone and successor set,  and then either a pointer gets updated on the entity's IRI entry, or a pointer gets updated on the dataset point to the entity's IRI, or both.


This is an interesting approach to handling **immutable RDF** while maintaining the **succession of states** for entities and their relationships. By introducing indirection and a concept of **relator succession**, you can manage updates efficiently without modifying the original triples, which aligns well with an immutable data philosophy.

Here’s a breakdown of how this approach might work and how it could be integrated into your Kosmion ontology:

### Key Components for Implementing Relator Succession:
1. **Relator Series/Succession**:
   - This involves creating a **series of related relators**, each representing an updated state of a particular relationship or entity.
   - Each new version of a **micro-dataset** that replaces the previous one would include an **updated pointer** that points to the latest version.
  
2. **Using Tombstones and Successor Relations**:
   - When a **new micro-dataset** is created (for an update), the previous version receives:
     - A **tombstone marker** (e.g., `:tombstone` with a timestamp).
     - A reference to its **successor** (e.g., `:relator-successor`), pointing to the newly created version.
   - This effectively chains the datasets, allowing a traversal to find the latest state while preserving historical data.

3. **Indirection and Mutable Pointers**:
   - **Mutable pointers** could be implemented by having a designated **IRI** that always points to the current/latest micro-dataset for an entity. This IRI would not change, but the underlying **pointer** (an RDF statement) would be updated to reference the latest version.
   - Alternatively, the **dataset itself** could include a mutable pointer that directs to the entity’s IRI or vice versa.

### Practical Example Using Dave Richardson Data
To implement this for the **Dave Richardson** entity, consider introducing a relator mechanism that manages updates:

#### Current Dataset:
```turtle
@prefix : <https://djradon.github.io/dave-richardson/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix prov: <http://www.w3.org/ns/prov#> .

<https://djradon.github.io/dave-richardson/> rdfs:label "Dave Richardson (Person)" ;
    a foaf:Person ;
    foaf:name "Dave Richardson" ;
    foaf:homepage <https://djradon.github.io/> ;
    prov:wasDerivedFrom <https://djradon.github.io/dave-richardson/v0> ;
    .
```

#### Next Version with Tombstone and Successor:
Assume we need to update the homepage. A new micro-dataset would be created:

```turtle
@prefix : <https://djradon.github.io/dave-richardson/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix prov: <http://www.w3.org/ns/prov#> .

<https://djradon.github.io/dave-richardson/v1> rdfs:label "Dave Richardson (Person)" ;
    a foaf:Person ;
    foaf:name "Dave Richardson" ;
    foaf:homepage <https://new-homepage.com/> ;
    prov:wasDerivedFrom <https://djradon.github.io/dave-richardson/v0> ;
    .

<https://djradon.github.io/dave-richardson/v0> :tombstone "2024-10-12T12:00:00Z"^^xsd:dateTime ;
    :relator-successor <https://djradon.github.io/dave-richardson/v1> ;
    .
```

#### Indirection Using Mutable Pointer
Instead of changing `<https://djradon.github.io/dave-richardson/>` directly, it could point to the latest **versioned dataset**:

```turtle
<https://djradon.github.io/dave-richardson/> :latestVersion <https://djradon.github.io/dave-richardson/v1> .
```

This way:
- The IRI `<https://djradon.github.io/dave-richardson/>` always stays the same, acting as an **anchor** for the entity.
- The actual data is versioned, and changes are handled through **succession relations** and **tombstones**.

### Benefits of This Approach:
1. **Immutability**:
   - RDF data remains **immutable**, ensuring that historical states are preserved.
  
2. **Version Control**:
   - Users or agents querying the data can easily traverse the **succession chain** to understand how the data has evolved over time.

3. **Clear Historical Provenance**:
   - Using **PROV-O** properties like `prov:wasDerivedFrom` makes it easy to trace the origins of each version.

### Considerations:
- **Query Complexity**: Tracking the latest state involves traversing the chain of successors or following the **mutable pointer**.
- **Storage Overhead**: Each update results in a new micro-dataset, which could lead to increased storage requirements, although it guarantees immutability.

This solution provides a structured way to maintain immutable RDF data while still allowing for updates, and it could be very powerful in the context of **Kosmion**. Would you like to expand on this or add these mechanisms to your current draft?


## The IRIs have to stay the same. :latestVersion is one approach, "mutable pointer", and it's a good one, but a) you have to keep changing it (so it's not consisten with immutability elsewhere, I guess it's okay to have 2 classes of IRIs, ), b) there's no date information so bitemporal timetravel is tricky. Is there any mechanism in RDF for a "dataset series"? Maybe named graphs could work, with the tombstone attached to the named graphs.

### Addressing Immutable RDF and Dataset Series

For implementing an immutable RDF approach while keeping **IRIs consistent** across versions, here are some mechanisms that could help, including considerations for **dataset series** and how **named graphs** could be leveraged.

### Challenge:
- **IRIs need to remain consistent** for entities, while **updates** should be managed in a way that preserves immutability.
- You are considering two classes of IRIs: 
  - **Mutable pointers** (e.g., pointing to the latest version) for practical purposes.
  - **Immutable identifiers** that do not change, representing entities throughout time.
- **Bitemporality** complicates matters because tracking both **transaction time** and **valid time** requires information about when the dataset was valid as well as when it was recorded.

### Possible Mechanisms to Implement Dataset Series

#### 1. **Named Graphs for Relator Series**:
- Use **named graphs** to manage **dataset series**. Each named graph could represent a specific **version** of the data, including metadata such as a **tombstone** or **validity timestamps**.
- Named graphs make it possible to define the **scope** of triples, allowing you to group all the data about a specific version under a named IRI.

##### Example with Named Graphs:
```turtle
@prefix : <https://djradon.github.io/dave-richardson/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix prov: <http://www.w3.org/ns/prov#> .

GRAPH <https://djradon.github.io/dave-richardson/v1> {
    <https://djradon.github.io/dave-richardson/> rdfs:label "Dave Richardson (Person)" ;
        a foaf:Person ;
        foaf:name "Dave Richardson" ;
        foaf:homepage <https://djradon.github.io/> ;
        prov:generatedAtTime "2024-10-12T12:00:00Z"^^xsd:dateTime ;
        .
}

GRAPH <https://djradon.github.io/dave-richardson/v2> {
    <https://djradon.github.io/dave-richardson/> rdfs:label "Dave Richardson (Person)" ;
        a foaf:Person ;
        foaf:name "Dave Richardson" ;
        foaf:homepage <https://new-homepage.com/> ;
        prov:wasDerivedFrom <https://djradon.github.io/dave-richardson/v1> ;
        prov:generatedAtTime "2024-11-01T08:00:00Z"^^xsd:dateTime ;
        .
}

<https://djradon.github.io/dave-richardson/v1> :tombstone "2024-11-01T08:00:00Z"^^xsd:dateTime ;
    :relator-successor <https://djradon.github.io/dave-richardson/v2> ;
    .
```
In this example:
- Each named graph (`v1`, `v2`) represents a specific version of the **Dave Richardson** dataset.
- The **IRI** (`<https://djradon.github.io/dave-richardson/>`) remains consistent across versions, but the different graphs manage successive states.
- The `:tombstone` property marks when the graph version is considered "invalid" or "superseded."

#### 2. **Dataset Series Using DCAT and Versioning**:
- You could use **DCAT (Data Catalog Vocabulary)** to describe a **series of datasets** that make up the entire **relator succession**.
- Each version can be represented as a **distribution** of a dataset, with specific properties that define its **validity period** and **system time**.

##### Example Using DCAT:
```turtle
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .

<https://djradon.github.io/datasets/dave-richardson> a dcat:Dataset ;
    dct:title "Dave Richardson Dataset Series" ;
    dcat:distribution <https://djradon.github.io/datasets/dave-richardson/v1> , <https://djradon.github.io/datasets/dave-richardson/v2> .

<https://djradon.github.io/datasets/dave-richardson/v1> a dcat:Distribution ;
    dct:issued "2024-10-12T12:00:00Z"^^xsd:dateTime ;
    dct:validUntil "2024-11-01T08:00:00Z"^^xsd:dateTime ;
    dcat:accessURL <https://djradon.github.io/dave-richardson/v1> .

<https://djradon.github.io/datasets/dave-richardson/v2> a dcat:Distribution ;
    dct:issued "2024-11-01T08:00:00Z"^^xsd:dateTime ;
    dcat:accessURL <https://djradon.github.io/dave-richardson/v2> .
```
Here:
- The dataset (`<https://djradon.github.io/datasets/dave-richardson>`) acts as a **series** of distributions, each representing a **specific version**.
- **`dct:issued`** and **`dct:validUntil`** help manage the temporal aspects for each version.

#### 3. **Using PROV-O for Temporal Succession**:
- Use **PROV-O** to manage the relationships between successive versions and handle bitemporal aspects.
- Each version of a dataset can use properties like:
  - **`prov:wasDerivedFrom`** to point to the previous version.
  - **`prov:generatedAtTime`** for system time.
  - **`prov:invalidatedAtTime`** to mark when a version becomes obsolete.

### Pros and Cons of Named Graphs for Dataset Series
- **Pros**:
  - Named graphs allow each version of the data to be **self-contained**, making it easy to represent a **succession of states**.
  - By attaching metadata like `:tombstone` and `prov:wasDerivedFrom` to the named graph, you can manage both the **valid time** and **system time** aspects, supporting bitemporal requirements.
- **Cons**:
  - Managing and querying **multiple named graphs** can become complex, especially if your dataset series grows significantly.
  - RDF stores must support **named graphs** efficiently for this to be practical.

### Summary
- The **named graph** approach combined with **PROV-O** and **DCAT** provides a robust way to manage **immutable RDF** while allowing for versioning and temporal tracking.
- You can manage **IRIs consistently** by having them always point to a conceptual entity, while the **version information** is managed separately in named graphs.
- The **tombstone** mechanism, along with **mutable pointers** like `:latestVersion`, helps balance immutability with practical requirements for updates.

Let me know if you’d like to incorporate any of these ideas into your Kosmion ontology or if you’d like me to make specific updates to the current draft to reflect this!


