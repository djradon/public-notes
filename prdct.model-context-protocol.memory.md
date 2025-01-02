---
id: 6ktu4sml44iy84ikwipjik2
title: Memory
desc: ''
updated: 1735605097732
created: 1735604966248
---


## t.2024.12.30.16

Core Concepts
Entities

Entities are the primary nodes in the knowledge graph. Each entity has:

    A unique name (identifier)
    An entity type (e.g., "person", "organization", "event")
    A list of observations

Example:

{
  "name": "John_Smith",
  "entityType": "person",
  "observations": ["Speaks fluent Spanish"]
}

Relations

Relations define directed connections between entities. They are always stored in active voice and describe how entities interact or relate to each other.

Example:

{
  "from": "John_Smith",
  "to": "Anthropic",
  "relationType": "works_at"
}

Observations

Observations are discrete pieces of information about an entity. They are:

    Stored as strings
    Attached to specific entities
    Can be added or removed independently
    Should be atomic (one fact per observation)

Example:

{
  "entityName": "John_Smith",
  "observations": [
    "Speaks fluent Spanish",
    "Graduated in 2019",
    "Prefers morning meetings"
  ]
}