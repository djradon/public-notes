---
id: 13s2lqwflayx6ft508wgzpw
title: Atomic Data
desc: 'use all knowledge of the world as if it were a big JSON object'
updated: 1714165880666
created: 1714115290895
---

## Comparisons

## vs [[prdct.rdf]]

-   Atomic calls the three parts of a Triple `subject`, `property` and `value`, instead of `subject`, `predicate`, `object`.
-   Atomic does not support having multiple statements with the same `<subject> <predicate>`, every combination must be unique.
-   Atomic does not have `literals`, `named nodes` and `blank nodes` - these are all `values`, but with different datatypes.
-   Atomic uses `nested Resources` and `paths` instead of `blank nodes`
-   Atomic requires URL (not URI) values in its `subjects` and `properties` (predicates), which means that they should be resolvable. Properties must resolve to an `Atomic Property`, which describes its datatype.
-   Atomic only allows those who control a resource's `subject` URL endpoint to edit the data. This means that you can't add triples about something that you don't control.
-   Atomic has no separate `datatype` field, but it requires that `Properties` (the resources that are shown when you follow a `predicate` value) specify a datatype. However, it is allowed to serialize the datatype explicitly, of course.
-   Atomic has no separate `language` field.
-   Atomic has a native Event (state changes) model ([Atomic Commits](https://docs.atomicdata.dev/commits/intro)), which enables communication of state changes
-   Atomic has a native Schema model ([Atomic Schema](https://docs.atomicdata.dev/schema/intro)), which helps developers to know what data types they can expect (string, integer, link, array)
-   Atomic does not support Named Graphs. These should not be needed, because all statements should be retrievable by fetching the Subject of a resource. However, it _is_ allowed to include other resources in a response.

## vs [[prdct.solid]]

**similar goals** to Atomic Data:

-   Decentralize the web
-   Make things more interoperable
-   Give people more control over their data

Technically, both are also similar:

-   Usage of **personal servers**, or PODs (Personal Online Datastores). Both Atomic Data and Solid aim to provide users with a highly personal server where all sorts of data can be stored.
-   Usage of **linked data**. All Atomic Data is valid RDF, which means that **all Atomic Data is compatible with Solid**. However, the other way around is more difficult. In other words, if you choose to use Atomic Data, you can always put it in your Solid Pod.

But there are some important **differences**, too, which will be explained in more detail below.

-   Atomic Data uses a strict built-in schema to ensure type safety
-   Atomic Data standardizes state changes (which also provides version control / history, audit trails)
-   Atomic Data is more easily serializable to other formats (like JSON)
-   Atomic Data has different models for authentication, authorization and hierarchies
-   Atomic Data does not depend on existing semantic web specifications
-   Atomic Data is a smaller and younger project, and as of now a one-man show
   
### [Atomic Data is more easily serializable to other formats (like JSON)](https://docs.atomicdata.dev/interoperability/solid#atomic-data-is-more-easily-serializable-to-other-formats-like-json)

Atomic Data is designed with the modern (web)developer in mind. One of the things that developers expect, is to be able to traverse (JSON) objects easily. Doing this with RDF is not easily possible, because doing this requires _subject-predicate uniqueness_. Atomic Data does not have this problem (properties _must_ be unique), which means that traversing objects becomes easy.

Another problem that Atomic Data solves, is dealing with long URLs as property keys. Atomic Data uses `shortnames` to map properties to short, human-readable strings.

For more information about these differences, see the previous [RDF chapter](https://docs.atomicdata.dev/interoperability/rdf).

### [Authentication](https://docs.atomicdata.dev/interoperability/solid#authentication)

Both Solid an Atomic Data use URLs to refer to individuals / users / Agents.

Solid's identity system is called WebID. There are multiple supported authentication protocols, the most common being [WebID-OIDC](https://github.com/solid/webid-oidc-spec).

Atomic Data's [authentication model](https://docs.atomicdata.dev/authentication) is more similar to how SSH works. Atomic Data identities (Agents) are a combination of HTTP based, and cryptography (public / private key) based. In Atomic, all actions (from GET requests to Commits) are signed using the private key of the Agent. This makes Atomic Data a bit more unconventional, but also makes its auth mechanism very decentralized and lightweight.

### Solid advantages

-   No inbox or [notifications](https://www.w3.org/TR/ldn/) yet ([issue](https://github.com/ontola/atomic-data/issues/28)) ([[prdct.linked-data-notifications]])
-   No OIDC support yet. ([issue](https://github.com/atomicdata-dev/atomic-server/issues/277))
-   No support from a big community, a well-funded business or the inventor of the world wide web.

## Shortnames

- Requiring Properties to resolve is part of what enables the type system of Atomic Schema - they provide the shortname and datatype.

### Advantages of Shortnames

Readability: Shortnames can make your transactions and queries more concise and easier to understand, especially when dealing with complex Property names.
Brevity: They reduce data size in transaction payloads.
Potential Namespace Management: Shortnames can play a role in how you manage namespaces within your data model.

### Important Considerations

- Name Collisions: Atomic Data guarantees uniqueness of the Subject-Property combination, mitigating shortname collisions within the context of an entity. However, if resources from multiple Classes with the same shortname are mixed, clients need a strategy to resolve potential clashes (see the Atomic Data FAQ you linked earlier).
- Not a Replacement for Full URIs: Shortnames are a convenience mechanism. Internally, Atomic Data still relies on full Property URIs.
- each Property URL must resolve to an online Atomic Data Property.


## References

- https://docs.atomicdata.dev/interoperability/solid