---
id: gtdd0u5ibhtg0dri5w6bzg5
title: Kv012
desc: ''
updated: 1728796245769
created: 1728795953615
---


## What's the best way to specify a "backup URI" for an ontology

- paraphrase: rdfs:isDefinedBy or owl:seeAlso

## could I just specify multiple owl:versionIRIs ?

In RDF/OWL, each ontology version can only have one `owl:versionIRI` property. It uniquely identifies that specific version of the ontology. Specifying multiple `owl:versionIRIs` would break the principle of having a clear and unambiguous version identifier.

However, you can use other properties to specify additional URIs for the ontology, such as:
- **`rdfs:seeAlso`** to link to related URIs or backups.
- **`owl:priorVersion`** for linking to previous versions, effectively creating a chain.
- **Custom properties** like `:backupURI` if you want a dedicated property.

For example:
```turtle
<https://kosmion.github.io/ont/v0/kosmion-v0.ttl> a owl:Ontology ;
    owl:versionIRI <https://kosmion.github.io/ont/v0/kosmion-v0.1.2.ttl> ;
    rdfs:seeAlso <https://kosmion.github.io/ont/backup/kosmion-backup.ttl> .
```

This allows you to point to a backup without conflicting with the versioning structure of OWL. Let me know if this works for you or if you need a different solution!

## I guess owl:versionIRI could be applied to regular "a-box" RDF files too.