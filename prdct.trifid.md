---
id: 5s2dskuhqq5w8ikcp36no4c
title: Trifid
desc: 'lightweight and easy way to access Linked Data URIs via HTTP, '
updated: 1729873416266
created: 1714109080591
---

- https://zazuko.com/products/trifid/
- [[c.software.semantic.browser]] [[c.software.semantic.publishing.site-generator]]
- repo: https://github.com/zazuko/trifid
- written_in: javascript
- published-by: [[org.zazuko]]
- built_on: [[prdct.node]]
![[prdct.pubby#^4ldbidz2j6c8]]

## Requirements

- SPARQL endpoint, or
- triple in a local file (uses built-in in-memory store)

## Features

-   Provides a Linked Data interface to SPARQL protocol servers
-   Provides an in-memory store suitable for smaller data sets and testing environments
-   Provides a simple HTML interface showing the data available about each resource
-   Support for multiple HTML templates based on namespace patterns
-   HTML view is providing embedded JSON-LD, which is rendered by client-side JavaScript
-   Takes care of content-negotiation
-   Runs well behind HTTP reverse proxies like Varnish
-   Provides a SPARQL proxy and [YASGUI](http://about.yasgui.org/)
