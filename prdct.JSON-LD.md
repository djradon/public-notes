---
id: rgof5gwgwgrz3vp3394kfmq
title: JSON-LD
desc: ''
updated: 1706727235106
created: 1636178352439
similar: prdct.yaml-ld
---


- [[p.isComparandOf]] https://sookocheff.com/post/api/on-choosing-a-hypermedia-format/

## Features

### Keywords

- @id keyword allows you to give a node a URI
- @context lets you define vocabulary references
- @import "Context files are imported/re-used by creating the context as an array where the first value(s) is the path(s) to the imported context, followed by an object" (https://www.w3.org/TR/json-ld-syntax/#the-context).
  - https://www.w3.org/TR/json-ld/#imported-contexts
- Each of the JSON-LD keywords, except for @context, may be aliased to application-specific keywords.


Resources:
- https://github.com/fairsharing/jsonldschema
- https://www.baeldung.com/json-linked-data
  - mentions: [[prdct.hydra]]

References:
- https://www.w3.org/TR/json-ld