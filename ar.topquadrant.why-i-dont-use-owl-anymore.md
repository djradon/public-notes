---
id: n3nb7chx9s16p158u9d6eoh
title: Why I Dont Use Owl Anymore
desc: ''
updated: 1722731249759
created: 1720723041466
---

- https://www.topquadrant.com/resources/why-i-dont-use-owl-anymore/
- author: @irene-polikoff
- related: [[ar.topquadrant.why-i-use-shacl-for-defining-ontology-models]]

## Highlights

- "The only parts of RDFS I use are subclasses."
- "OWL reasoning is primarily about classification e.g., given information about a resource we can infer what class or set it belongs to."
- Key Issues:
  - open world assumption
  - confusion around reasoning
  - having too much (features) and yet not enough

### Open World Assumption


### Confusion around Reasoning


### Not Enough Features

- there is still no way in it to make definitions that are very commonly needed. For example, you can’t say that:

* person’s full name must equal a concatenation of their first and last names
* duration is the difference between the end and start dates
* start date can’t be greater than the end date

  - Anything that involves some operations can’t be stated. This means that key parts of what one would commonly want to express in a model can only be written in either application code or a rules language proprietary to a given RDF tool.