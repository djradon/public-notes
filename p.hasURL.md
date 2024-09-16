---
id: BzaAaifsfEv5mTiEOFBPA
title: hasURL
desc: ''
updated: 1698275345015
created: 1630795517106
---

- [[p.alsoKnownAs]] is associated with URL; webpage; URL;
- [[p.equivalentPredicate]] [vcard:hasURL](http://www.w3.org/2006/vcard/ns#hasURL)

## use of "URL"

### [[p.vs]] URI

- [What's the Difference Between a URI and a URL?](https://danielmiessler.com/study/difference-between-uri-url/) :
  - "If the protocol (https, ftp, etc.) is either present or implied for a domain, you should call it a URL—even though it’s also a URI."

- the terms URI and IRI might represent more general and accessible concepts, but

### [[p.vs]] site

- [c] better to use [[p.hasSite]] when appropriate? 
  - t.2023.04.08 Why? You can probably tell from the URL whether there's a site to back things up. keep it simple

## possible alternatives

## [[p.vs]] [[vcard:url]]

- url is shorter than hasUrl
- hasUrl probably reads better

## [[p.vs]] `foaf.homepage` 

"Has URL" is like `foaf.homepage`, but homepage (in the sense of a personal web site) feels almost antiquated. 

### "homepage" [[p.hasSense]] 

- the "first page you go to on a site",
  - i.e. the high-effort page nobody sees any more
- the browser home page

##  [[p.vs]] identifier

- [Data Model - schema.org](https://schema.org/docs/datamodel.html#identifierBg)
  - "in most cases there is a conventional short name for most identifier schemes"
  - unrelated: "we do not treat isicV4 as a subproperty of identifier since it serves to identify a category not an individual Thing" -- categories need identifiers too!
    - [2021-10-20] I think what I meant here was "categories are things too"





