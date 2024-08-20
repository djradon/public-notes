---
id: hkgnl85l3ma8mfma0jykw3z
title: Workflow Engine
desc: ''
updated: 1724192578977
created: 1724189715756
---

## I'm looking for a workflow engine for world simulation and a role-playing experience platform. Must be open source. ideally would integrate with semantic web technologies. 


Given your requirements for a workflow engine suitable for world simulation and a role-playing experience platform that is open-source and ideally integrates with semantic web technologies, here's a tailored evaluation of the options you've listed:

### Top Recommendations:

#### 1. **Zeebe / Camunda**
   - **Strengths**: Zeebe, especially as part of Camunda's offerings, is designed for high-throughput and distributed environments, making it a strong candidate for complex simulations and large-scale role-playing platforms. It supports BPMN 2.0 and is well-suited for microservices and event-driven architectures, which are often required in dynamic simulation environments.
   - **Integration with Semantic Web**: Camunda has a flexible API and can be integrated with other systems, including those using RDF or OWL for semantic data. However, it doesn’t natively support semantic web technologies out-of-the-box.
   - **Considerations**: Requires some effort to integrate with semantic web technologies, but its scalability makes it a top choice for large, complex workflows.

#### 2. **Flowable**
   - **Strengths**: Flowable is another BPMN engine that is highly extensible and supports CMMN (Case Management Model and Notation) for more dynamic, case-based workflows. This could be beneficial for the non-linear nature of role-playing scenarios.
   - **Limitations**: The open-source version has some limitations, especially regarding enterprise features, but it still provides a strong base for BPMN/CMMN workflows.
   - **Integration with Semantic Web**: Like Zeebe, integration with semantic web technologies would need to be custom-built, but the flexibility of Flowable might make this easier.

### Other Considerations:

#### 3. **Kogito (Red Hat)**
   - **Strengths**: Built on top of Drools, Kogito focuses on cloud-native and event-driven applications, which is beneficial for world simulations. It also supports BPMN, DMN (Decision Model and Notation), and is designed to be highly flexible.
   - **Integration with Semantic Web**: Kogito is designed with a modern architecture that could be extended to integrate with semantic web technologies. Its close ties with Drools (a rules engine) can also add more complex logic capabilities to your workflows.

#### 4. **Drools**
   - **Strengths**: A powerful rules engine that can handle complex logic, which is often required in simulation environments. Drools integrates well with BPMN, making it possible to handle complex workflows with intricate decision logic.
   - **Integration with Semantic Web**: While not directly supporting semantic web technologies, Drools is highly customizable and could be integrated with RDF/OWL through custom code.

### Niche Options:

#### 5. **Behavior Tree**
   - **Strengths**: Well-suited for AI-driven behavior modeling, which could be useful in simulation aspects of your platform. It’s more of a lower-level solution compared to BPMN engines.
   - **Limitations**: Lacks the broader workflow management features provided by BPMN engines, making it less suitable if you need comprehensive process management.

#### 6. **Temporal**
   - **Strengths**: Temporal provides a microservices-friendly workflow engine that excels in handling stateful long-running workflows.
   - **Limitations**: While powerful, it’s more focused on microservices orchestration and may require significant customization to fit a simulation and role-playing platform.

#### 7. **Elsa**
   - **Strengths**: Elsa is a modern, .NET-based workflow engine with a focus on extensibility and easy integration into .NET applications.
   - **Limitations**: The lack of certain features like multi-tenancy and "hot" deployable workflow packages might be limiting, but it is a promising option for .NET-centric environments.

### Final Recommendation:
If you are leaning towards a BPMN-based engine that can scale well and has broad support for complex workflows, **Zeebe/Camunda** or **Flowable** would be your best bet. For a rules-engine-centric approach, **Kogito** or **Drools** could be ideal, especially if you anticipate needing extensive decision logic.

Given the importance of integrating with semantic web technologies, these engines would require some custom development to fully meet your needs, particularly if you plan on leveraging RDF/OWL-based ontologies within your workflow engine.

Each of these tools has strengths that could be beneficial depending on your specific requirements, so considering how these align with your overall architecture and technology stack will help you make the best choice.


## do any support CMMN other than flowable?

As of now, **Flowable** is one of the few open-source workflow engines that supports CMMN (Case Management Model and Notation). Most other workflow engines focus primarily on BPMN (Business Process Model and Notation) or DMN (Decision Model and Notation) and do not natively support CMMN.

### Specific Details:
1. **Flowable**:
   - **CMMN Support**: Flowable supports CMMN alongside BPMN and DMN. This makes it particularly strong for case management scenarios where workflows are not strictly predefined and can start in various states or evolve dynamically.
   - **Open Source**: Flowable offers its CMMN capabilities in the open-source version, though some advanced features may require the enterprise edition.

### Engines Without CMMN Support:
1. **Zeebe / Camunda**:
   - **Focus**: Zeebe (and by extension, Camunda) focuses heavily on BPMN for workflow management and DMN for decision management. It does not natively support CMMN.
   
2. **Kogito**:
   - **Focus**: Kogito, built on top of Drools, supports BPMN and DMN but does not offer CMMN capabilities.

3. **Activiti**:
   - **Focus**: Activiti focuses on BPMN and has some support for DMN but does not support CMMN natively.

### Summary:
If CMMN support is a crucial requirement for your project, **Flowable** is your primary open-source option. It is well-suited for applications that require flexible case management alongside traditional BPMN workflows. For other engines like Zeebe, Camunda, or Kogito, you would need to explore workarounds or custom implementations if you require CMMN-like functionality.

## the flexibility of cmmn is attractive for modeling RPG-style games, but visual-only notation seems imprecise and impractical. is there a textual alternative?

CMMN (Case Management Model and Notation) is indeed a powerful tool for modeling flexible and non-deterministic workflows, such as those found in RPG-style games. However, as you've identified, its visual notation can be imprecise and impractical for certain use cases. For those seeking a more textual or code-based approach, there are a few alternatives and strategies you might consider:

### 1. **CMMN XML Representation**:
   - **Textual Format**: While CMMN is often used with graphical tools, it is inherently based on XML. You can directly author or manipulate CMMN models using XML, which provides a textual, precise, and version-controllable way to define cases.
   - **Tooling Support**: Many CMMN-compliant tools allow you to export and edit CMMN models as XML files. This gives you the ability to define your models textually, though it requires familiarity with the XML schema of CMMN.

### 2. **Declarative Workflow Languages**:
   - **Declarative Languages**: If you are looking for flexibility similar to CMMN but with a focus on textual representation, declarative workflow languages like **[[prdct.declare]]** (or languages inspired by it) might be of interest. Declare is designed for specifying constraints rather than fixed sequences of tasks, which aligns well with the flexibility of RPG scenarios.
   - **Pros**: These languages offer a balance between flexibility and precision, allowing you to define rules and constraints textually while maintaining the non-deterministic nature of the workflows.

### 3. **Drools Rule Engine**:
   - **Rules-Based Approach**: Using a rules engine like **Drools** allows you to define complex conditions and actions in a textual format. This can be particularly powerful for RPG-style games where game states and outcomes can be managed through a set of rules rather than a predefined workflow.
   - **Integration with BPM**: Drools integrates well with BPM engines, allowing you to combine the flexibility of rules with more structured workflows.

### 4. **Scripting Languages in Game Engines**:
   - **Custom Scripting**: Many RPG-style games use custom scripting languages (e.g., Lua, Python) embedded within game engines to define the flow of gameplay. These languages can offer the same flexibility as CMMN but with the added benefit of being tailored to game development.
   - **Pros**: Scripting languages offer precise control over game mechanics, are highly flexible, and can easily integrate with other game components.

### 5. **Textual Modeling Languages (TML)**:
   - **Textual DSLs**: Some modeling tools offer Textual DSLs (Domain-Specific Languages) that provide the power of models with the flexibility of code. These DSLs allow you to define workflows, rules, and cases in a textual format that can be transformed into executable models.
   - **Example**: Xtext is a framework that allows you to create textual DSLs for various domains, including workflow modeling. This approach could be customized to reflect CMMN-like flexibility while maintaining the precision of textual notation.

### 6. **Business Process Model and Notation (BPMN) with Extensions**:
   - **Textual BPMN**: BPMN itself can be represented in XML and manipulated textually. Additionally, some tools allow for extensions to BPMN that can capture more dynamic, case-like behavior while still using a textual format.
   - **Pros**: This approach leverages the widespread tooling and support for BPMN while introducing the flexibility needed for more dynamic scenarios.

### Conclusion:
For RPG-style game modeling, where flexibility is crucial, using a declarative language like **Declare**, a rules-based approach with **Drools**, or even custom scripting in game engines may be more suitable than relying on visual CMMN notation alone. These options offer the textual precision you’re looking for, combined with the flexibility needed for complex, non-linear workflows.

If you still prefer to stay within the CMMN ecosystem, directly working with **CMMN XML** provides a more hands-on, text-based approach to defining your models.

## has anyone done an OWL ontology for CMMN concepts?

It seems that no comprehensive OWL ontology specifically for CMMN (Case Management Model and Notation) concepts has been widely adopted or documented. While there are tools and research efforts aimed at integrating CMMN with other semantic technologies, a dedicated OWL ontology capturing the full range of CMMN concepts appears to be a niche or yet-to-be-developed area.

However, creating such an ontology is feasible and could be beneficial for projects requiring semantic interoperability between case management systems and other ontological frameworks. If you're considering this, you might need to start from the foundational concepts of CMMN and build an ontology that captures the core elements such as cases, stages, tasks, milestones, and sentries, possibly extending existing business process ontologies.

For existing tools, you may find partial mappings or semantic annotations in tools like Trisotech or other business process modeling environments that could serve as a starting point.

## can you site some existing business process ontologies?

Certainly! There are several established ontologies in the domain of business processes that have been developed to model various aspects of business process management, workflows, and related concepts. Here are some notable examples:

### 1. **Business Process Model and Notation (BPMN) Ontology**
   - **Description**: Several ontologies have been developed to model BPMN concepts. These ontologies typically capture BPMN elements like tasks, events, gateways, and the relationships between them.
   - **Examples**:
     - **BPMN 2.0 Ontology**: Developed to map BPMN 2.0 concepts to OWL. It includes classes for process elements like activities, events, and flows.
     - **Process Ontology by Hepp and Roman**: An early attempt to create a comprehensive ontology for business processes based on BPMN.
   - **Use Case**: Useful for integrating BPMN diagrams with semantic web technologies, enabling automated reasoning over business processes.

### 2. **Process Specification Language (PSL)**
   - **Description**: PSL is an ontology developed by NIST (National Institute of Standards and Technology) to represent the semantics of process descriptions. It aims to facilitate interoperability between different process-related applications.
   - **Components**: PSL includes concepts like activities, states, timepoints, and objects, which can be used to describe processes in a standardized way.
   - **Use Case**: Standardization and interoperability in manufacturing, engineering, and other industries where process descriptions need to be shared across systems.

### 3. **Enterprise Ontology**
   - **Description**: Developed as part of the Enterprise Project, this ontology captures core business concepts, including organizational structure, activities, processes, and resources.
   - **Components**: Includes a comprehensive set of concepts related to enterprise functions, such as roles, goals, and processes.
   - **Use Case**: Business process modeling, organizational modeling, and enterprise architecture.

### 4. **REA (Resources, Events, Agents) Ontology**
   - **Description**: The REA ontology is based on the REA accounting model, which is used for modeling economic resources, events, and agents involved in business transactions.
   - **Components**: Key concepts include resources, events, agents, commitments, and contracts.
   - **Use Case**: Accounting and financial modeling, particularly in the context of enterprise resource planning (ERP) systems.

### 5. **The Semantic Business Process Management (SBPM) Ontology**
   - **Description**: SBPM aims to semantically enhance traditional business process management by integrating ontological concepts. It includes concepts from BPMN and extends them with semantic annotations.
   - **Components**: Process, activity, role, goal, and data are among the key concepts.
   - **Use Case**: Enhancing BPM systems with semantic reasoning capabilities, improving process automation and compliance.

### 6. **DOLCE+DnS Ultralite (DUL)**
   - **Description**: While not specifically a business process ontology, DUL (a lightweight version of the DOLCE ontology) includes a framework for describing events and processes in a generic way. It has been used as a foundation for developing domain-specific ontologies, including those related to business processes.
   - **Components**: Concepts include actions, plans, roles, tasks, and events.
   - **Use Case**: Provides a formal ontological framework that can be extended for domain-specific applications, including business processes.

### 7. **Value Delivery Modeling Language (VDML) Ontology**
   - **Description**: VDML is a standard developed by the Object Management Group (OMG) for modeling value creation and delivery in business processes. The VDML ontology captures the key concepts of this modeling language.
   - **Components**: Concepts include value propositions, activities, roles, and deliverables.
   - **Use Case**: Modeling value networks and business ecosystems, analyzing value creation in business processes.

### Summary:
These ontologies offer a range of tools for modeling different aspects of business processes. Depending on your specific needs—whether you’re focusing on workflow management, enterprise architecture, or economic transactions—one of these ontologies or a combination of them might be suitable for your project. If you are interested in CMMN-specific concepts, you may consider extending one of these ontologies or developing a new one that integrates with CMMN's case management concepts.