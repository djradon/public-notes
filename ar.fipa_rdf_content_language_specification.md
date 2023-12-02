---
id: og8bk3c5ikxqyny89c3q0m4
title: Fipa_rdf_content_language_specification
desc: ''
updated: 1701517208268
created: 1701516222365
url: (http://www.fipa.org/specs/fipa00011/XC00011B.html)
---

## Thoughts

- for actions, the action "verb" is just a text string
- foreshadowing of rdf-star:

## Examples

### Belief

```
  <fipa:Proposition>

    <rdf:subject>TCP/IP Illustrated</rdf:subject>

    <rdf:predicate rdf:resource="http://description.org/ schema#author"/>

    <rdf:object>W. Richard Stevens</rdf:object/>

    <fipa:belief>true</fipa:belief>

  </fipa:Proposition>
```

### Action

```
@prefix fipa: <http://www.fipa.org/schemas#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .

<http://issemantic.net/#JohnAction1> a fipa:Action ;
    fipa:act "open" ;
    fipa:actor "John" ;
    fipa:argument [ a rdf:bag ;
            rdf:_1 "door1" ;
            rdf:_2 "door2" ] .
```

