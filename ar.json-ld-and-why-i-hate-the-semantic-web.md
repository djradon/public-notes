---
id: svak6dc31aevjrz7qb7pn8u
title: JSON-LD and Why I Hate the Semantic Web
desc: ''
updated: 1726254140530
created: 1726180292094
---

- http://manu.sporny.org/2014/json-ld-origins-2/ (dead)
  - https://web.archive.org/web/20230524052750/http://manu.sporny.org/2014/json-ld-origins-2/

## Summary

The desire for better Web APIs is what motivated the creation of JSON-LD, not the Semantic Web. If you want to make the Semantic Web a reality, stop making the case for it and spend your time doing something more useful, like actually making machines smarter or helping people publish data in a way that’s useful to them.

## Highlights

- "Precious time is spent in groups discussing how we can query all this Big Data that is sure to be published via RDF instead of figuring out a way of making it easy to publish that data on the Web by leveraging common practices in use today. Too much time is spent assuming a future that’s not going to unfold in the way that we expect it to. That’s not to say that TURTLE, SPARQL, and Quad stores don’t have their place, but I always struggle to point to a typical startup that has decided to base their product line on that technology"
- "RDF is a shitty data model. It doesn’t have native support for lists." ^m9yunsigu2uc

## Comments

- @ruben-verborgh: "Isn’t it rather content types/schemas/profiles that we need for interoperability—and that’s it?"
  - @manu-sporny: "Computer/Data scientists have this misguided notion that you need a data model for something to be useful. I believe this notion typically comes from the scientific desire to have things rigorously defined and predictable, which isn’t necessarily a bad thing, but it drives people toward nailing something down before it’s really necessary."
  - @manu-sporny: "To answer your other questions, no, developers don’t want to transform their JSON properties to URIs just for the sake of doing it. They do want to be able to merge and combine data sources, though. You can have universal meaning without having a rigorously defined data model. For example, just making the JSON properties map to URIs and giving a JSON object and identifier of some kind is enough. You don’t need RDF. That’s all you need to give the object universal meaning, everything else is icing on the cake."


## References

- https://www.reddit.com/r/programming/comments/38f6b1/jsonld_and_why_i_hate_the_semantic_web/