---
id: dp4w7jmpsawbe3rj7kxa7sf
title: 37 Multi Level
desc: ''
updated: 1728704483170
created: 1724871721394
---

- https://github.com/nemo-ufes/gufo/issues/37

- @andre-demori: "Hello, I am working on a conceptual model using UFO constructs that is also based on Multi-Level Theory.

However, when I import gUFO, I am encountering a problem when defining attribute values ​​(data properties) for Individuals that are also types (punning).

However, it seems that gUFO does not support MLT, since properties that are classified as hasQualityValue can only be defined for an Individual and not for a type. When I do this, the reasoner says that there is an ontological inconsistency.

Therefore, I would like to know if you have already encountered this problem and if there is an immediate solution. If not, I would like to leave this recommendation for future extensions."

- @joao-paulo-almeida:  Indeed, gUFO enforces a dichotomy between types and individuals. This means that types can't bear aspects (as only concrete individuals can). A workaround is to use regular object/data properties.

We have been discussing a possible relaxation of some of the domain/range declarations (e.g., the domain of gufo:hasQualityValue and the range of gufo:inheresIn) to include types in addition to concrete individuals. This would be an easy way to accommodate the view of types as endurants and would not impact existing gUFO-based ontologies.

(See [[ar.incorporating-types-of-types-in-ontology-driven-conceptual-modeling]] for how we address types as endurants in UFO more broadly.)