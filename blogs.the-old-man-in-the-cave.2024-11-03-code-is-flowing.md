---
id: 6d0cdipyv5jxdbs615ssb32
title: '2024-11-03: Code Is Flowing'
desc: sf-cli Lives!
updated: 1730744837711
created: 1730646458171
---

*We could live in that waterfall.*

I just started a new conversation with ChatGPT. In response to its “What can I help with?”, I gave a rather impersonal message: “blog update about my semantic flow cli.” Usually I’m a bit friendlier.

Without my asking, it filled a canvas with [[a suggested update|sfow.conv.2024-11-03-chatgpt-lame-update-semantic-flow-cli]] that I hated before even looking at it. Then I tried to read it and started finding falsehoods and lameness everywhere.

Yes, I’m hostile to synthetic prose. But ChatGPT at least gave me a skeleton and the motivational annoyance to get things going. So for experiment’s sake, the meat of this update is going to be a rewrite of ChatGPT’s intolerable draft. 

I’ll admit though... I’m curious to hear its feedback. Maybe I’ll post it in the comments.


[![The Midnight Sun](/assets/images/2024-11-03-07-51-56.png)](https://djradon.github.io/wiki/notes/74xz2kw8sjpc5ifkske9z3c/)
<small>Norma pouring some precious water, from *[[video.twilight-zone.s03e10-the-midnight-sun]]*</small>

---

To my four subscribers and posterity:

I’m reluctantly sharing an update about the [Semantic Flow CLI](https://github.com/semantic-flow/sf-cli) I’ve been bumbling through. At the moment, this under-designed command-line tool will set up a folder hierarchy and a configuration file for a [[semantic site “root” repository|sflow.concepts.sf-root-repo]], the foundation of the Semantic Flow RDF versioning and self-publishing methodology. I’m excited to be in the flow with an actual piece of software, I’m eager to get back to it, and the kids need breakfast. So I’ll try to make this quick.

## Semantic Flow CLI: Key Features

### Reference Pages for De-referenceable entity IRIs

You may know that Semantic Web data is composed of triples that link together resources. The subject is the resource being described. The predicate is a property resource that defines the relationship. And an object is another resource that is related to the subject. 

For two examples:

```turtle
:the-old-man-in-the-cave :helped :goldsmith .
```

You may also know that an IRI is a URL that supports international characters and doesn’t necessarily locate a web page, although it should. IRIs are how resources are identified (or uniquely named, if you prefer) on the Semantic Web.

The above examples use namespacing to hide the full IRI, which otherwise might look something like this:

```turtle
<https://djradon.github.io/the-old-man-in-the-cave> <https://djradon.github.io/ns/d/helped> <https://djradon.github.io/ns/d/goldsmith> .
```

From the [[t.cs.web.w3c]]’s [[ar.w3.rdf-1-1-concepts-and-abstract-syntax]] recommendation: “Any IRI or literal denotes something in the world (the "universe of discourse"). These things are called resources. Anything can be a resource, including physical things, documents, abstract concepts, numbers and strings; the term is synonymous with "entity" as it is used in the RDF Semantics specification. The resource denoted by an IRI is called its referent...” and “The IRI owner can establish the intended referent by means of a specification or other document that explains what is denoted... A good way of communicating the intended referent is to set up the IRI so that it dereferences to such a document.”

Semantic Flow can generate these documents. I’m calling them reference pages.

### Namespace and IRI curation

Semantic Flow is about publishing RDF data, and useful RDF resources need a namespace, a place where their identifiers can live and be made legible. I’d like to be able to create [[git repositories of semantic data|sflow.concepts.sf-data-repo]] that can define and populate [[namespaces|sflow.concepts.namespace]] in a [[Semantic Flow site|sflow.concepts.site]] with a single deft command, or at worst a series of prompts.

### Dataset Series Handling

The central conceit of Semantic Flow is that every entity worth its salt should be associated with at least two [[sets of versioned datasets|sflow.concepts.dataset-series.vset]]: a [[catalog series|sflow.concepts.dataset-series.catalog]] and a [[default series|sflow.concepts.dataset-series.default]]. Grouping dataset versions into a series is the heart of Semantic Flow, and the CLI will help automate version bumps at the entity level. When changes are made to entity data (in the default series or otherwise), sf-cli can update the corresponding catalog automatically.

### Template Integration

When generating the HTML [[reference pages|sflow.concepts.reference-pages]], you should be able to apply one or more templates to effectively convey information visually and make the pages usable. 

## Tech Stack

I’m building the CLI using Deno, which has been a frustrating experience so far, no fault of Deno’s. Eventually, Deno’s ability to run untrusted remote code in a hopefully-secure way might be a great foundation for composable, interactive [alternate realities](https://theoldmaninthecave.substack.com/p/lets-reboot-the-semantic-web-with-alternate-realities). 

I’m using [[prdct.cliffy]] for the command-line framework although I keep glancing at [[prdct.oclif]] and [[prdct.inquirer]].

## Challenges

From smallest to biggest: 

- Dealing with [Cliffy and Deno release candidate compatibility](https://github.com/c4spar/deno-cliffy/issues/763) has been tricky.

- The CLI only has one command so far and it’s already a ball of razors in need of decomposition.

- [[sflow.concepts.immutability]] holds a great deal of promise for data management. See [XTDB’s walkthrough](https://docs.xtdb.com/tutorials/immutability-walkthrough/part-1.html) for some insight. But I’m doing a lot of mental hand-waving right now: Will entity references in Semantic Flow-compatible RDF data have to specify the version they’re referring to? Or can some kind of software reasoner figure it out based on context? 

## What’s Next?

- importing existing [[Data Repos|sflow.concepts.sf-data-repo]] into a [[Root Repo|sflow.concepts.sf-root-repo]]
- scanning Data Repos for covered IRIs and minting some primitive [[sflow.concepts.reference-pages]]
- [[sflow.products.ontology]] with classes and properties to support this whole effort
- docs with clarifying examples

I’m expecting to get a beta version out... no time soon. ChatGPT has been a valuable, tireless coding partner, but I could use more than its credulous efforts to get things flowing. So please reach out if you’re a javascript code reviewer or seasoned ontologist.