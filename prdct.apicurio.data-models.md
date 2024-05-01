---
id: bsgn8cu42xy85h6oe6gk6ru
title: Data Models
desc: 'Java and TypeScript compatible library that provides reading, writing, analysis, modification, and validation of OpenAPI and AsyncAPI documents'
updated: 1714580807805
created: 1714580696637
---

- https://www.apicur.io/datamodels/


## Features

### Parsing into a formal model

OpenAPI and AsyncAPI content, typically JSON or YAML, can be parsed into a formal, structured tree-like data model, much like XML or other structured content.

### Visitor + Traverser patterns

Full support for the [visitor design pattern](https://en.wikipedia.org/wiki/Visitor_pattern), for a single node in the model, and also an up or down traversal of the full or partial document.

### Validation of the model

Validate all or part of the data model against all of the rules defined in the OpenAPI or AsyncAPI specifications.

### Supports both Java and TypeScript

Use this library in your Java, Node.js, or browser-based applications! It works the same no matter how you use it.

### Convert OpenAPI 2.0 to OpenAPI 3.0

Includes a built-in transformer for easily converting older Swagger documents into the newer OpenAPI 3 format.

### Robust $ref support

Provide your own $ref resolver so that the library can properly analyze or validate documents with external references. Also includes a built-in dereferencer, which can transform a document with external references into one without any by internalizing all of the refs!