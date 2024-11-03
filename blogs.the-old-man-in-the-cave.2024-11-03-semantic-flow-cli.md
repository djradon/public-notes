---
id: 6d0cdipyv5jxdbs615ssb32
title: Semantic Flow CLI
desc: ''
updated: 1730649701210
created: 1730646458171
---

I just started a new conversation with ChatGPT: "blog update about my semantic flow cli." Without my asking, it filled a canvas with a suggested update that I hated before even looking at it. Then I tried to read it and started finding falsehoods, annoyances, and lameness everywhere.

I prize my writing as something original and human, so I'm biased against synthetic prose. But it is an easy way to get things going, even if it's just providing an enemy to oppose.

For experiment's sake, the rest of this update is going to be a rewriting of chatgpt's draft. I'm going to limit myself to ol' ChatGPT's structure, but rewrite each sentence in defiance. 

---

To my four subscribers and posterity:

I'm reluctantly sharing an update about the [Semantic Flow CLI](https://github.com/semantic-flow/sf-cli) I've been bumbling through. At the moment, this under-designed command-line tool will set up a folder hierarchy and a configuration file for a [[semantic site git repository|sflow.concepts.sf-root-repo]], which might eventually become the foundation of an RDF versioning and self-publishing methodology. I don't want to get too distracted and the kids need breakfast, so I'll make this quick.

**Key Features Under Development:**

1. **Namespace Management**: Semantic Flow is about publishing RDF data, and RDF data needs a namespace, a place where all those resource IRIs can live. This means you can create namespaces in your Semantic Flow repository with just a single command, streamlining the whole process.

2. **Dataset Series Handling**: Managing versioned datasets and dataset series is at the heart of Semantic Flow, and the CLI is being designed to automate these version bumps across the board. When changes are made, you can update the corresponding catalogs automatically—no need to dig through multiple files or manually track changes.

3. **Template Integration**: The CLI supports applying templates from the ‘templates’ folder in a consistent manner across all generated RDF resources. If you want a unified look or consistent metadata across your generated static site, this feature will take care of it.

**Tech Stack**: I'm building the CLI using Deno, which has been a great experience so far, especially with TypeScript support out of the box. Deno's security model and easy module imports have been a big plus. I'm also using Cliffy for handling the interactive aspects of the CLI—it's helping make the user experience smooth and efficient.

**Challenges**: One of the more interesting challenges I'm working through is the need for both stability and flexibility in version management. There’s a balance to be found between keeping track of everything as it evolves, but also providing 'current' and 'next' indicators that make it easy for developers to know which version they should be using.

**What's Next?**
- I plan to expand support for **SFRootRepo management**, allowing users to easily configure new root repositories for their Semantic Flow sites.
- I'm looking at ways to **better handle cross-repo references** so that multiple repositories can contribute individuals and datasets in a unified namespace without chaos.

If you’re interested in following along or contributing, I’d love to hear your feedback. I’m aiming to get a beta version out soon, and your thoughts could really help shape how it develops.