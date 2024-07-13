---
id: fkw5wantovnjm6twrvrpsx0
title: Why I Use Shacl for Defining Ontology Models
desc: ''
updated: 1720737602961
created: 1720723924914
---

- https://www.topquadrant.com/resources/why-i-use-shacl-for-defining-ontology-models/
- author: @irene-polikoff

## Highlights

- "When you create a model in SHACL, you do not need to think whether you should use rdfs:subClassOf or owl:equivalentClass in defining restriction on property values."
  - related: https://stackoverflow.com/questions/65052036/what-is-the-difference-between-owlequivalentclass-and-rdfssubclassof-when-maki
    - "Semantically, you are defining the class as Primitive (subClassOf) versus Defined (equivalentClass). The main difference is in inferencing in one or both directions.

    The Primitive class is single direction:

        any Thing with ShipsTo with values from Italy can be inferred to be a deliversToItaly 
    
    The Defined class is both directions:
        as above, and
        any Thing that is a deliversToItay can be inferred to have shipTo with values from Italy

    A Defined class is used when you are confident that you have necessary and sufficient rules for class membership - otherwise Primitive is used for necessary rules only."
  - t.2024.07.11.12 but OWL doesn't define restriction in the same way as shacl
- [ ] While you could use types from OWL to say that a property is an Object or a Datatype property, SHACL does not consider this. It will be looking only at the constraints specified in the shape e.g., datatype and class constraints!