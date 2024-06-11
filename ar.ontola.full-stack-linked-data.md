---
id: jhopk9p3diourocvkbdeswf
title: Full Stack Linked Data
desc: ''
updated: 1718064020048
created: 1714185941710
---

- https://ontola.io/blog/full-stack-linked-data
- related: [[prdct.ndjson]]


## Highlights

- CTO @thom-van-kalkeren thoroughly studied the principles behind REST, HATEOS and Hypermedia, and concluded that we need to give everything URLs. Not just the pages that we present to our users, but every single thing that can be used by a client - including menu items, buttons, actions and form fields.
- [[prdct.linked-delta]]
- the RDF representation of data can be created during serialization - so your app can create linked data without using a triple store! ^mzabxzsavtsd

### Why Linked Data?

-   **Browsable**. Using links for everything in data, means that data can be surfed like how web pages work: just follow the URLs. That's actually really helpful in a web application, since this means that the client no longer needs to be aware of your routing logic.
-   **Flexibility**. Everything can be serialized to various formats (JSON, XML, Turtle, N-Triples, and [more](https://ontola.io/blog/rdf-serialization-formats/)), which gives some really nice and flexible export functionality.
-   **Self-describing APIs**. Simply use content-type negotiation to fetch a resource as HTML or some RDF format, and browse the data like you would browse a website: by following the links. API docs become kind of unnecessary, since navigating the website shows you all the endpoints.
-   **Re-use other linked data**. Because links can point to _anywhere_ (not just your server), you can use all the publicly available linked data! This, for me, has always been the number one reason to believe in Linked Data.
-   **Enables true data ownership**. Because of this, it enables _decentralized networks_ where people _own their data_, which can help to combat the existing web oligopoly. That's what the [Solid project](https://ontola.io/solid) is all about.
-   

### Why not use SPARQL?

- [[prdct.sparql]] is the de facto query language for RDF data, so it seems logical to use it somewhere in our stack. However, we don't. 
  - Getting SPARQL performant is actually pretty difficult, and we don't need the powerful query options that it provides. 
  - Most of the requests from the front-end just ask for all triples about one or multiple subjects, and these kind of queries don't require SPARQL. 
  - SPARQL is useful for more complex graph property traversal queries, but is not necessarily the best approach for simpler queries.