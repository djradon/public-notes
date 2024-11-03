---
id: 6d0cdipyv5jxdbs615ssb32
title: Semantic Flow CLI
desc: ''
updated: 1730660784167
created: 1730646458171
---

I just started a new conversation with ChatGPT: "blog update about my semantic flow cli." Without my asking, it filled a canvas with [[a suggested update|sf.conv.2024-11-03-chatgpt-lame-update-semantic-flow-cli]] that I hated before even looking at it. Then I tried to read it and started finding falsehoods, annoyances, and lameness everywhere.

I prize my writing as something human so I'm biased against incorporating synthetic prose. But it is an easy way to get things going, even if it's just providing an enemy to oppose. 

For experiment's sake, the rest of this update is going to be a rewriting of chatgpt's draft. I'm going to limit myself to ol' ChatGPT's structure, but rewrite each sentence in defiance. 

---

To my four subscribers and posterity:

I'm reluctantly sharing an update about the [Semantic Flow CLI](https://github.com/semantic-flow/sf-cli) I've been bumbling through. At the moment, this under-designed command-line tool will set up a folder hierarchy and a configuration file for a [[semantic site "root" repository|sflow.concepts.sf-root-repo]], the foundation of an RDF versioning and self-publishing methodology. I'm proud to be making progress on an actual piece of software (and the kids need breakfast) so I'll make this quick.

**Key Features Under Development:**

1. **Namespace and IRI curation**: Semantic Flow is about publishing RDF data, and useful RDF resources need a namespace, a place where their identifiers can live. I'd like to be able to create [[git repositories of semantic data|sflow.concepts.sf-data-repo]] that can define and populate [[namespaces|sflow.concepts.namespace]] in a [[Semantic Flow site|sflow.concepts.site]] with a single deft command, or at worst a series of prompts.

2. **Dataset Series Handling**: The central conceit of Semantic Flow is that every entity worth its salt should be associated with at least two [[versioned set of datasets|sflow.concepts.dataset-series.vset]]: a [[catalog|sflow.concepts.catalog]] and a [[sflow.concepts.dataset-series.default]]  Managing versioned datasets and dataset series is at the heart of Semantic Flow, and the CLI is being designed to automate these version bumps across the board. When changes are made, you can update the corresponding catalogs automatically—no need to dig through multiple files or manually track changes.

3. **Template Integration**: The CLI supports applying templates from the ‘templates’ folder in a consistent manner across all generated RDF resources. If you want a unified look or consistent metadata across your generated static site, this feature will take care of it.

**Tech Stack**: I'm building the CLI using Deno, which has been a great experience so far, especially with TypeScript support out of the box. Deno's security model and easy module imports have been a big plus. I'm also using Cliffy for handling the interactive aspects of the CLI—it's helping make the user experience smooth and efficient.

**Challenges**: One of the more interesting challenges I'm working through is the need for both stability and flexibility in version management. There’s a balance to be found between keeping track of everything as it evolves, but also providing 'current' and 'next' indicators that make it easy for developers to know which version they should be using.

**What's Next?**
- I plan to expand support for **SFRootRepo management**, allowing users to easily configure new root repositories for their Semantic Flow sites.
- I'm looking at ways to **better handle cross-repo references** so that multiple repositories can contribute individuals and datasets in a unified namespace without chaos.

If you’re interested in following along or contributing, I’d love to hear your feedback. I’m aiming to get a beta version out soon, and your thoughts could really help shape how it develops.