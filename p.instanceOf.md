---
id: s2AA4w4SyPFu44ylTFLQH
title: instanceOf
desc: the subject is a concrete example of a Class
updated: 1710803997355
created: 1633270478774
---

#ontology

- [[p.alsoKnownAs]] isA, is a, is an instance of the class
- [[p.hasDomain]] [[c.resource]]
- [[p.hasRange]] [[c.class]]
- [[p.equivalentPredicate]] [rdf:type](http://www.w3.org/1999/02/22-rdf-syntax-ns#type)
- [[p.inverseOf]] ???
  - [-] important thing to have a name for, maybe "hasInstance"  or classOf
    - maybe not so important, when do classes need to refer to their instances? backlinks provides inventory 
  - sometimes things (topics primarily/only) can be classes, without being Classes.
  
  
## instanceOf Discussion

- changed because 
  - "instanceOf" underscores that the subject is not a Class
    - t.2024.03.18.16 unless it's an instanceOf a class
  - it feels like, colloquially, "type" is ambiguous between hasType and isTypeOf; the latter can mean  something more like subClassOf
- isA is nice and compact, but maybe feels ambiguous for classes, e.g. "[a] digital garden is a website" 
- https://stackoverflow.com/questions/25737584/subclassof-and-instance-of-rdf-rdfsclass

## log

- [x] #gd replace all in-Class occurences of instanceOf that have Class subjects with subClassOf
  t.2022.12.12 there was only one... [[c.dsl]]