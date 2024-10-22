---
id: 5ehoz90tfa8ky2k4j60ocgp
title: Edtf
desc: ''
updated: 1729633731428
created: 1729617841866
---

## On https://id.loc.gov/datatypes/EDTFScheme.html why don't they have a scheme for level 3?

The Library of Congress does not define a scheme for EDTF Level 3 in their linked data service because the existing EDTF implementation only supports Levels 0, 1, and 2. These levels focus on progressively more complex features, such as uncertain or approximate dates, and partial unspecified dates. However, Level 3 in EDTF introduces more advanced and flexible features, like fuzzy time intervals and indefinite time spans, which are not as widely adopted or implemented in various systems.

This might explain why they chose not to include Level 3—likely due to its complexity and the fact that not all systems are prepared to handle such flexible or imprecise data representations. In practice, Levels 0 through 2 are often sufficient for most cataloging and metadata needs, especially for libraries and linked data services like the one offered by the Library of Congress【22†source】【23†source】【25†source】. 

For your use case, if you want to support Level 3, you'll need to define your datatype independently, given that it's not handled by the LOC scheme.

## I want to do a datatype for EDTF. EDTF has 4 levels, but I don't think there are any semantic incompatibilities between the levels. Any reason to define different data types for different levels? 

If the four levels of EDTF (Extended Date/Time Format) don’t introduce semantic incompatibilities between the levels, there might not be a strong reason to define separate datatypes for each level. Here’s a breakdown of considerations to help decide:

### 1. **Consistency Across Levels:**
   If the four levels of EDTF represent increasing specificity or additional features without fundamentally changing the interpretation of the format (e.g., level 0 is a simple date, while level 1 adds support for uncertain dates, etc.), then a single datatype can handle all levels. You can define one `EDTF` datatype and rely on validation mechanisms (such as SHACL) to ensure that the literal conforms to the appropriate EDTF level.

### 2. **Validation and Parsing:**
   One argument for splitting datatypes would be if different processing or validation logic is required for each level. For example, if the constraints (such as regex or structural validation) differ significantly for each level, defining separate datatypes would make it easier to enforce level-specific rules. However, if all levels can be parsed and validated with a shared approach (like a broader regex pattern that matches all levels), then one datatype might suffice.

### 3. **Tooling and Interoperability:**
   Some RDF tools might behave better with more granular datatypes if there are processing rules or validators that need to differentiate between levels. But if you plan to handle the EDTF logic internally (e.g., with SHACL validation), a single datatype is simpler and easier to maintain.

### 4. **Future Flexibility:**
   If there’s a chance that different levels might diverge semantically in the future, or you foresee needing specific level-aware logic, you could preemptively define separate datatypes now. This would give you flexibility but at the cost of added complexity.

### Conclusion:
Given that there’s no immediate semantic conflict between the levels and that validation could likely be handled with a single mechanism, defining a single datatype for `EDTF` seems like the simplest and most efficient approach. You can still rely on regex patterns or SHACL rules to enforce the proper format for specific use cases.

Would you like to see an example of how you might define an EDTF datatype in RDF and SHACL?


## namespace design

- @dave:

I'm going to use github to host a namespace for EDTF and define the datatype. I've created an organization "edtf-datatype", and I'll use a repo called edtf-datatype.github.io to host a dereferencable site on github pages. So the namespace will start with "https://edtf-datatype.github.io/". Should I add "/ns" to that path, so the IRI for the datatype would be "https://edtf-datatype.github.io/ns/edtf"? Or something else? Or just "https://edtf-datatype.github.io/edtf"

- chatgpt:

Adding `/ns` to your namespace path is a common practice, as it clearly distinguishes the namespace itself from other resources (like documentation or other public assets) that might be hosted under the same domain. This separation helps keep the namespace clean and easily recognizable.

However, it's not strictly necessary. You could go with either:

- **With `/ns`:**
  - Namespace: `https://edtf-datatype.github.io/ns/`
  - Datatype IRI: `https://edtf-datatype.github.io/ns/edtf`
  - This approach keeps the option open to define multiple namespaces in the future, and it's clearer that this part of the URL is dedicated to RDF/ontology content.

- **Without `/ns`:**
  - Namespace: `https://edtf-datatype.github.io/`
  - Datatype IRI: `https://edtf-datatype.github.io/edtf`
  - This approach is simpler and might be more lightweight for a small project if you're sure that the repository will only focus on this single datatype or related vocabularies.

### Considerations:
1. **Scalability**: If you might expand the project later to include additional vocabularies or resources, having `/ns` could help you organize things better.
2. **Clarity**: The `/ns` in the path helps signal that this is an RDF/ontology namespace and avoids potential collisions if you use the base path for other purposes (e.g., serving an HTML site).
3. **Simplicity**: If you're sure the project scope will remain small, skipping `/ns` results in a cleaner, shorter IRI.

### Recommendation:
If there's any possibility that you'll host multiple namespaces or related resources in the future, using `https://edtf-datatype.github.io/ns/edtf` would be more scalable and organized. Otherwise, if it's only for a single datatype, keeping it simple with `https://edtf-datatype.github.io/edtf` is perfectly fine.


## Are there any EDTF implementations that support level 3?

There are a few implementations of EDTF that partially support Level 3 features, but it's less commonly implemented compared to Levels 0 through 2. 

For example, the **Python EDTF2 library** supports parsing most of the EDTF levels, including some Level 3 features like season intervals and extended ranges, which are particularly useful for bibliographic applications. However, Level 3 is not fully standardized across tools, so some implementations may support it in a limited or experimental capacity [^32] [^33].

Additionally, **EDTF.js** offers partial support for Level 3, particularly for advanced features like season intervals, which are important for certain use cases. The creators of the library have mentioned that Level 3 features require careful handling in validation, and their approach is to allow for some flexibility by combining levels where appropriate (e.g., Level 0 + Level 3) [^33] [^34].

However, there is no comprehensive validation service or tool that fully supports Level 3 across all features. The University of North Texas (UNT) provides a validation service for Levels 0, 1, and 2, but it explicitly does not support Level 3 [^35].

If you're planning to work with Level 3 in an EDTF context, you may need to extend or customize existing libraries depending on your specific needs.

## Interestingly, the Library of Congress ontologies all define their subjects as datatypes, classes, AND individuals. 

Yes, it's quite interesting that many Library of Congress ontologies define subjects as **datatypes**, **classes**, and **individuals** simultaneously. This is an unusual modeling choice that reflects the desire for **multi-faceted descriptions** of terms in linked data.

1. **Datatypes**: The Library of Congress (LOC) might define a subject as a datatype to support the notion that specific literal values can be associated with it, enabling the use of the subject in places where typed literal values are required (e.g., for metadata encoding or validation).

2. **Classes**: Defining the subject as a class allows it to be used as a general category for grouping resources or entities. This means that other entities can be classified under this subject, establishing broader and more abstract relationships.

3. **Individuals**: Defining a subject as an individual allows it to be treated as a concrete, identifiable entity, which is useful in contexts where specific references or assertions about that entity are required.

This approach reflects a certain flexibility in RDF modeling that allows the same entity to play different roles depending on the context. It’s particularly useful in the cultural heritage and bibliographic domains where the same concept may need to function as both a classifying category (class) and a specific instance of something (individual) for different types of metadata or use cases【22†source】【24†source】【26†source】.

Would you like more details on how this impacts the design of ontologies?

## Another interesting thing in those EDTF ontologies is this:

- @dave: 
  
[ rdf:type owl:Ontology
 ] .

at the top of the file. What's the purpose of that?

- chatgpt:

The statement `[ rdf:type owl:Ontology ] .` at the top of an RDF or OWL file is a declaration that the document or graph itself is of the type `owl:Ontology`. This serves several important purposes:

### 1. **Ontology Identification**:
   By declaring that the file is of type `owl:Ontology`, it clearly marks the document as being an OWL ontology. This is useful for tools that process RDF/OWL, as they can recognize and handle the file as an ontology instead of some other type of RDF data (e.g., instance data or a different kind of schema).

### 2. **Metadata Declaration**:
   The `owl:Ontology` element allows you to provide metadata about the ontology itself, such as:
   - **Versioning information** (`owl:versionIRI`)
   - **Creators** (`dc:creator` or `dc:contributor`)
   - **License** (`cc:license`)
   - **Imports** of other ontologies (`owl:imports`)
   This can help in managing the ontology lifecycle, version control, and ensuring proper attribution and reuse.

### 3. **Consistency with OWL Semantics**:
   OWL provides specific reasoning capabilities and semantic rules that apply to ontologies. Declaring the document as an ontology ensures that it will be processed with OWL semantics in mind, which can affect how inferencing, consistency checking, and other reasoning tasks are performed.

### 4. **Tool Compatibility**:
   Many ontology editing and reasoner tools (such as Protégé, OWL API, or other RDF processors) expect an explicit `owl:Ontology` declaration. It ensures that these tools can handle the file properly, recognizing it as a formal description of concepts, classes, properties, and relationships rather than a set of instance data or a different type of RDF structure.

In summary, the purpose of `[ rdf:type owl:Ontology ] .` is to formally declare that the file defines an ontology, enabling proper processing, identification, and management of the ontology metadata across different systems and tools.


## What is the purpose of owl:NamedIndividual

The purpose of `owl:NamedIndividual` in OWL (Web Ontology Language) is to explicitly declare an entity as a **named individual** within the ontology. Here's how it fits into OWL:

### 1. **Distinguishing Individuals from Classes and Properties**:
   `owl:NamedIndividual` is used to clearly indicate that a particular entity is an **instance** of one or more classes, not a class or a property. In RDF, individuals are just entities (resources), but OWL uses `owl:NamedIndividual` to emphasize that an entity is a unique, concrete individual as opposed to an abstract class or property.

   Example:
   ```ttl
   :John rdf:type owl:NamedIndividual ;
         rdf:type :Person .
   ```
   This example states that `:John` is an individual of type `Person`.

### 2. **Facilitating Reasoning**:
   OWL reasoners use `owl:NamedIndividual` to infer facts about individuals and perform logical operations. Declaring individuals in this way helps reasoners differentiate between individuals and classes, ensuring they apply appropriate logic for individual-based reasoning.

   For instance, OWL can infer relationships between individuals (e.g., that two individuals are distinct, or that they have certain properties) when they're marked as `owl:NamedIndividual`.

### 3. **Disjointness of Classes and Individuals**:
   OWL’s semantics treat classes and individuals differently. By marking an entity as `owl:NamedIndividual`, you signal that the entity should not be confused with a class or property. For example, a person like `John` is an individual, while `Person` is a class. This distinction helps avoid incorrect inferences or modeling errors.

### 4. **Named vs. Anonymous Individuals**:
   `owl:NamedIndividual` specifically refers to **named individuals** (those with an IRI). In contrast, OWL also allows for **anonymous individuals** (or blank nodes), which don’t have a globally unique identifier but can still participate in relationships in the ontology. Using `owl:NamedIndividual` ensures that the individual has a distinct identity within the ontology.

In summary, `owl:NamedIndividual` serves to clearly indicate that an entity is a concrete, distinct individual within an OWL ontology, which is important for reasoning, distinguishing individuals from classes, and ensuring correct semantic interpretation of relationships.


## It seems a little redundant to distinguish something as having an IRI. That can be surmised from the context. Is there an example where owl:NamedIndividual is useful?



## In my Kosmion ontology, where I want to minimize use of Classes and embrace things that are individuals and classes, owl:NamedIndividual would be useful. Can you think of any places it could be useful. Remember, EDTF datatypes are classes and individuals

## References

- 

[^32]: https://pypi.org/project/edtf2/
[^33]: https://github.com/citation-style-language/schema/issues/421 
[^34]: https://www.librarianshipstudies.com/2016/05/extended-date-time-format-edtf.html
[^35]: https://digital2.library.unt.edu/edtf/