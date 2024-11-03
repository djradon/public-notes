---
id: 6d0cdipyv5jxdbs615ssb32
title: Semantic Flow CLI
desc: ''
updated: 1730667267106
created: 1730646458171
---

I just started a new conversation with ChatGPT. In response to its "What can I help with?", I gave a rather impersonal message: "blog update about my semantic flow cli." Without my asking, it filled a canvas with [[a suggested update|sf.conv.2024-11-03-chatgpt-lame-update-semantic-flow-cli]] that I hated before even looking at it. Then I tried to read it and started finding falsehoods, annoyances, and lameness everywhere.

Yes, I'm hostile to synthetic prose. But it is an easy way to get things going, even just as an enemy to indignantly oppose. But for experiment's sake, the rest of this update is going to be a rewriting of ChatGPT's crappy draft. 

I'll admit though... I'm curious to hear its feedback.

---

![](/assets/images/2024-11-03-07-51-56.png)


To my four subscribers and posterity:

I'm reluctantly sharing an update about the [Semantic Flow CLI](https://github.com/semantic-flow/sf-cli) I've been bumbling through. At the moment, this under-designed command-line tool will set up a folder hierarchy and a configuration file for a [[semantic site "root" repository|sflow.concepts.sf-root-repo]], the foundation of the Semantic Flow RDF versioning and self-publishing methodology. I'm proud to be making progress on an actual piece of software and the kids need breakfast, so I'll try to make this quick.

**Key Features Under Development:**

1. **De-referenceable entity IRIs**: From the [[t.cs.web.w3c]]'s [[ar.w3.rdf-1-1-concepts-and-abstract-syntax]] recommendation: "Any IRI or literal denotes something in the world (the "universe of discourse"). These things are called resources. Anything can be a resource, including physical things, documents, abstract concepts, numbers and strings; the term is synonymous with "entity" as it is used in the RDF Semantics specification. The resource denoted by an IRI is called its referent..." and "The IRI owner can establish the intended referent by means of a specification or other document that explains what is denoted... A good way of communicating the intended referent is to set up the IRI so that it dereferences to such a document." Semantic Flow can generate these documents. I'm calling them reference pages.

2. **Namespace and IRI curation**: Semantic Flow is about publishing RDF data, and useful RDF resources need a namespace, a place where their identifiers can live. I'd like to be able to create [[git repositories of semantic data|sflow.concepts.sf-data-repo]] that can define and populate [[namespaces|sflow.concepts.namespace]] in a [[Semantic Flow site|sflow.concepts.site]] with a single deft command, or at worst a series of prompts.

3. **Dataset Series Handling**: The central conceit of Semantic Flow is that every entity worth its salt should be associated with at least two [[versioned sets of datasets|sflow.concepts.dataset-series.vset]]: a [[catalog series|sflow.concepts.dataset-series.catalog]] and a [[default series|sflow.concepts.dataset-series.default]]. Grouping dataset versions into a series is the heart of Semantic Flow, and the CLI is helps automate version bumps at the entity level. When changes are made to entity data (in the default series or otherwise), sf-cli should update the corresponding catalog automatically.

4. **Template Integration**: When generating the HTML [[sflow.concepts.reference-pages]], you should be able to apply one or more templates to convey information visually and make the pages usable. 

5. **Tech Stack**: I'm building the CLI using Deno, which has been a frustrating experience so far. Eventually, Deno's ability to run untrusted remote code in a hopefully-secure way might be a great foundation for composing [[alternate realities|t.storytelling.alternate-reality]]. I'm using [[prdct.cliffy]] for the command-line framework, although I keep glancing at [[prdct.oclif]].

**Challenges**: [[sflow.concepts.immutability]] holds a great deal of promise for data management. See [XTDB's walkthrough](https://docs.xtdb.com/tutorials/immutability-walkthrough/part-1.html) for some insight. But I'm doing a lot of mental hand-waving right now: Will entity reference in RDF have to specify the version they're referring to? Or can some kind of software reasoner figure it out for us? 

**What's Next?**
- importing existing [[Data Repos|sflow.concepts.sf-data-repo]] into a [[Root Repo|sflow.concepts.sf-root-repo]]
- scanning Data Repos for covered IRIs and minting some primitive [[sflow.concepts.reference-pages]]

I’m expecting to get a beta version out... no time soon. ChatGPT has been a valuable, tireless coding partner, but I'm practically a beginner and I'll need more than its credulous efforts to get things flowing. So please reach out! 