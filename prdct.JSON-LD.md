---
id: rgof5gwgwgrz3vp3394kfmq
title: JSON-LD
desc: ''
updated: 1709251497698
created: 1636178352439
similar: prdct.yaml-ld
---


- [[p.isComparandOf]] https://sookocheff.com/post/api/on-choosing-a-hypermedia-format/

## Features

### Keywords

- @id keyword allows you to give a node a URI
- @context lets you define vocabulary references
- @import "Context files are imported/re-used by creating the context as an array where the first value(s) is the path(s) to the imported context, followed by an object" (https://www.w3.org/TR/json-ld-syntax/#the-context).
  - https://www.w3.org/TR/json-ld/#imported-contexts
- Each of the JSON-LD keywords, except for @context, may be aliased to application-specific keywords.

## Best Practices

- https://stackoverflow.com/questions/42398060/json-ld-to-normal-json
- http://niem.github.io/json/reference/json-ld/context/ discuss context, expansions, and contractions

### @chatgpt.4

what's the best practices for referencing other entities/objects in json-ld
ChatGPT

In JSON-LD, best practices for referencing other entities or objects include:

    Use of @id and @type Properties: Assign a unique identifier (@id) to each entity and specify its type (@type). This helps in clearly distinguishing and referencing different entities.

    Consistent and Descriptive Identifiers: Ensure identifiers are consistent and descriptive across your JSON-LD data. This aids in readability and maintainability.

    Utilizing Well-Known Contexts: Reference standard vocabularies or contexts (like schema.org) for common types and properties. This enhances compatibility and interoperability with other systems.

    Embedding vs. Linking: Decide whether to embed other objects directly or just link to them using their @id. Embedding can make the data self-contained, while linking keeps the JSON-LD document concise.

    Handling Multiple References: When referencing multiple entities, use an array of objects or identifiers. This keeps the structure organized and easy to parse.

    Contextualizing Relationships: Use descriptive property names that accurately represent the relationship between entities. This adds semantic clarity to your data.

    Maintaining JSON-LD Best Practices: Apart from referencing, follow general JSON-LD best practices like using a compact and readable format, validating your JSON-LD, and ensuring it aligns with the intended semantic meaning.

    Documentation: Document how references and entities are structured and related in your JSON-LD. This is crucial for others who will use or extend your data.

These practices help in creating a well-structured, understandable, and semantically rich JSON-LD document, facilitating better data integration and usage.



## Resources

- https://github.com/fairsharing/jsonldschema
- https://www.baeldung.com/json-linked-data
  - mentions: [[prdct.hydra]]

## References:
- https://www.w3.org/TR/json-ld
- https://json-ld.org/contexts/dollar-convenience.jsonld