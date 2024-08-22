---
id: rntox133e8g63tuw16jrfz0
title: '21'
desc: ''
updated: 1724281617204
created: 1724281561626
---

## are there published ontologies, similar to ontomedia or abc ontology, that describe fictional universes?

Ontologies specifically designed to describe fictional universes are relatively rare but have garnered interest in the academic and cultural heritage communities. These ontologies aim to capture the complex relationships, entities, and events within fictional narratives, allowing for structured analysis and data interoperability. Here are some notable examples:

### 1. **OntoMedia Ontology**
   - **Focus**: OntoMedia is designed to describe narratives, especially those in media and cultural contexts. It can be applied to fictional universes by modeling characters, events, places, and other narrative elements.
   - **Use Case**: It has been used in projects that involve the analysis and annotation of stories, particularly in media studies and digital humanities.

### 2. **ABC Ontology**
   - **Focus**: The ABC ontology was developed for managing multimedia resources and can be adapted to describe events, agents, and objects within fictional narratives.
   - **Use Case**: It’s been applied in digital library contexts but can be extended to model the structure and relationships within fictional worlds.

### 3. **Narrative Ontology (NOnt)**
   - **Focus**: NOnt is an ontology designed to represent narrative structures, including those found in fictional works. It focuses on events, characters, and their interactions within a story.
   - **Use Case**: NOnt can be used to model story arcs, character development, and plot structures in fictional narratives.

### 4. **LODE (Linking Open Descriptions of Events)**
   - **Focus**: LODE is an ontology designed to describe events, which can be adapted to describe events in fictional universes.
   - **Use Case**: It’s often used in cultural heritage projects to model historical events, but its structure is flexible enough to model fictional events in narratives.

### 5. **Fanfic Ontology**
   - **Focus**: Developed specifically to describe fanfiction, the Fanfic Ontology models relationships between characters, settings, and plot elements within fan-created stories.
   - **Use Case**: It captures the unique aspects of fan-created narratives, including the re-interpretation of existing fictional universes.

### 6. **SIOC (Semantically-Interlinked Online Communities) Ontology**
   - **Focus**: While not specifically designed for fictional universes, SIOC can be used to model online discussions, content, and communities that revolve around fictional works, including the relationships between characters, plots, and fan interpretations.
   - **Use Case**: SIOC is often applied to social media and online community content, making it adaptable for studying fictional universes through the lens of community engagement and fan culture.

### 7. **Storyspace Ontology**
   - **Focus**: The Storyspace Ontology is designed to model narrative structures, especially in the context of digital storytelling and interactive narratives.
   - **Use Case**: It can be applied to describe the structure of stories, including branching paths, character relationships, and narrative events in fictional universes.

### 8. **Myth Ontology**
   - **Focus**: This ontology is designed to describe mythological narratives, capturing the relationships between gods, heroes, and mythic events. While focused on mythology, it can be adapted to fictional universes with similar structures.
   - **Use Case**: Used in cultural heritage and anthropology to model mythological stories, which often have similarities to fictional universes in their complexity and scope.

### 9. **FOAF (Friend of a Friend) Ontology**
   - **Focus**: FOAF is not specifically designed for fictional universes, but it can be adapted to describe the relationships between characters in fictional settings.
   - **Use Case**: Commonly used to model social networks, FOAF can be applied to model the social relationships between characters in a fictional narrative.

### Summary:
While ontologies like OntoMedia and the ABC ontology are well-known for their application in narrative and multimedia contexts, other ontologies such as the Narrative Ontology, LODE, and even FOAF can be adapted to describe fictional universes. These ontologies provide structures for modeling events, characters, relationships, and other elements within fictional narratives, making them useful tools for projects that seek to analyze or manage fictional content.

## similar to the httpRange-14 issue: in the context of work, expression, manifestation, item -- an IRI could refer to any of those things. I almost feel like the IRI should contain the (primary) class of the thing. 

You're touching on a significant issue in the Semantic Web and digital humanities, especially in the context of the FRBR (Functional Requirements for Bibliographic Records) model, which introduces the concepts of Work, Expression, Manifestation, and Item (WEMI). This model is used to describe different levels of abstraction in bibliographic resources, but it can create ambiguity when using IRIs to identify these entities.

### The httpRange-14 Issue Analogy:
The httpRange-14 issue dealt with the ambiguity of IRIs on the web, specifically whether an IRI identifies a document or a concept described by that document. Similarly, in the WEMI model, an IRI could be ambiguous if it doesn't clearly indicate whether it refers to a Work, Expression, Manifestation, or Item.

### Should the IRI Contain the Class of the Thing?
Including the class (or type) in the IRI could help clarify the level of abstraction the IRI is meant to identify, but this approach has both pros and cons:

### **Pros of Including the Class in the IRI:**
1. **Disambiguation**:
   - Helps clarify what the IRI represents, reducing confusion about whether it refers to a Work, Expression, Manifestation, or Item.
   - Makes it easier for humans and machines to understand the nature of the resource directly from the IRI.

2. **Consistency**:
   - Encourages a consistent naming convention, which can make large datasets easier to manage and navigate.
   - Facilitates better data integration and linking across different datasets and ontologies.

3. **Ease of Querying**:
   - Improves the clarity of SPARQL queries, as the IRI itself provides hints about what kind of entity it identifies, potentially reducing the need for additional filtering or type checking.

### **Cons of Including the Class in the IRI:**
1. **Over-Specification**:
   - Embedding the class in the IRI can lead to a rigid structure, which might become problematic if the classification of an entity changes over time.
   - Limits flexibility in how entities are used or interpreted in different contexts.

2. **IRI Longevity**:
   - Best practices suggest that IRIs should be persistent and stable over time. If the class of an entity changes, having the class embedded in the IRI might necessitate changing the IRI, which could lead to issues with link rot or outdated references.

3. **Namespace Management**:
   - Managing namespaces with class-based IRIs could become cumbersome, especially in large and complex datasets where entities might belong to multiple classes or where class distinctions are not always clear-cut.

### Alternative Approaches:
Instead of embedding the class in the IRI, you could use other methods to disambiguate the entity type:

1. **Explicit Typing**:
   - Use RDF types (`rdf:type`) to explicitly declare the type of each entity. This keeps the IRI clean and allows for flexible classification.
   - Example:
     ```turtle
     :exampleWork a frbr:Work .
     :exampleExpression a frbr:Expression .
     ```

2. **Contextual Metadata**:
   - Provide additional metadata or contextual information alongside the IRI to clarify what the IRI refers to.
   - Use descriptive RDF properties that convey the specific nature of the resource (e.g., `dct:hasFormat`, `dct:isVersionOf`).

3. **Hierarchical Naming**:
   - Use a hierarchical or segmented naming convention within the IRI, which can suggest a broader context without strictly embedding the class.
   - Example: `http://example.org/resource/work/12345` vs. `http://example.org/resource/expression/12345`

4. **Use of URN/UUIDs**:
   - Consider using URNs or UUIDs as IRIs to avoid the issue of embedding type information. The type can be handled through metadata rather than within the IRI itself.

### Conclusion:
Including the class in the IRI can be a helpful way to disambiguate references to different levels of abstraction, especially in complex models like WEMI. However, it also introduces rigidity and potential challenges with IRI management. The best approach often depends on the specific needs of your project, the stability of your classifications, and how the IRIs will be used and maintained over time. Balancing clarity with flexibility is key, and sometimes a combination of clear IRIs and rich metadata provides the best of both worlds.