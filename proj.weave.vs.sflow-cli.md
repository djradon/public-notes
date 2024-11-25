---
id: j7vjddo0p5ll0w83hvw26z7
title: Sflow CLI
desc: ''
updated: 1732164219781
created: 1732164206585
---

Here's a comparison between **Weave** and **sflow-cli**, based on what they aim to do and their potential scope:

---

### **Weave**
**Purpose**:  
- A **general-purpose CLI tool** for managing and combining resources (e.g., syncing, merging, and managing files across multiple repositories or inclusion sources).
- Can operate independently of any specific static site generator (SSG), though it can integrate with them.

**Core Features**:
- **Inclusion Management**:
  - Sync files from multiple repositories into a common directory (`_combined` or equivalent).
  - Watch inclusion directories for changes and sync them dynamically.
- **Flexible Workflows**:
  - Developers can work directly in source repositories, with changes reflected in the combined output.
  - Global and per-inclusion options (e.g., include/exclude logic, suppression of copying).
- **SSG-Agnostic**:
  - Designed to support workflows for any SSG or standalone projects.
- **Extensibility**:
  - Open-ended functionality that could be expanded to support things like regex-based inclusion, version control helpers, or custom workflows.

**Key Focus**:  
Selective **combination** of resources and maintaining a smooth workflow for managing and syncing repositories.

---

### **sflow-cli**
**Purpose**:  
- A CLI tool tailored for **Semantic Flow** workflows, tightly integrated with RDF-based ontologies and publishing pipelines.
- Supports workflows for **Kosmion** and other RDF-centric projects.

**Core Features**:
- **Ontology Management**:
  - Tools for generating static sites based on RDF data, particularly Semantic Flow conventions.
- **Namespace Management**:
  - Handling RDF namespaces and dataset distribution.
- **Metadata Handling**:
  - RDF metadata generation, versioning, and validation for Semantic Flow sites.
- **Static Site Generation**:
  - Focused on creating RDF-driven sites using tools like Lume.

**Key Focus**:  
Managing **RDF-based ontologies and datasets** for publishing static sites.

---

### Differences
| Feature                        | **Weave**                             | **sflow-cli**                        |
|--------------------------------|----------------------------------------|---------------------------------------|
| **Scope**                      | General-purpose, SSG-agnostic         | RDF-specific, Semantic Flow-oriented |
| **File Handling**              | Inclusion/exclusion, syncing, merging | RDF data organization and publishing |
| **SSG Integration**            | Optional                              | Built for Semantic Flow workflows     |
| **Target Audience**            | Developers working with multi-repo projects | RDF and ontology enthusiasts         |
| **Main Use Case**              | Combining resources dynamically       | Generating static RDF-based sites    |

---

### Possible Interplay
- **Weave** could be used as part of a Semantic Flow pipeline to manage multi-repo inclusions.
- **sflow-cli** could then build the site from the combined output.

---

Would you like to refine the distinctions further or explore how they might complement each other?