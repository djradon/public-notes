---
id: hkf8qjlahs0imti0jlfwl3k
title: >-
  When You Use rdfs:type on Classes I Guess It Gets Back to the Difference
  between Superclass and Powerclass
desc: ''
updated: 1724512358477
created: 1720998565834
---

Sure! Below are examples of how to use `rdfs:subClassOf` and `rdfs:type` on classes in RDF using the Turtle syntax.

### 1. Superclass-Subclass Relationship

This example shows a superclass-subclass relationship where `Car` is a subclass of `Vehicle`.

```turtle
ex:Vehicle a rdfs:Class .

ex:Car a rdfs:Class ;
       rdfs:subClassOf ex:Vehicle .
```

### 2. Metaclass-Instance Relationship (Powertype)

This example demonstrates a metaclass-instance relationship where `Car` is an instance of the `VehicleType` metaclass.

```turtle
ex:VehicleType a rdfs:Class .

ex:Car a ex:VehicleType ;
       a rdfs:Class .
```

### Explanation

- **Superclass-Subclass Example**:
  - `ex:Vehicle` is defined as a class.
  - `ex:Car` is also defined as a class and is specified to be a subclass of `ex:Vehicle` using `rdfs:subClassOf`.

- **Metaclass-Instance Example**:
  - `ex:VehicleType` is defined as a class that serves as a metaclass (powertype).
  - `ex:Car` is defined as an instance of `ex:VehicleType` and also as a class itself.

### Complete Example with Both Concepts

To provide a more comprehensive example, here’s how both relationships can coexist in a single Turtle file:

```turtle
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix ex: <http://example.org/> .

# Define Vehicle as a class
ex:Vehicle a rdfs:Class .

# Define VehicleType as a metaclass
ex:VehicleType a rdfs:Class .

# Define Car as both a subclass of Vehicle and an instance of VehicleType
ex:Car a rdfs:Class ;
       rdfs:subClassOf ex:Vehicle ;
       a ex:VehicleType .
```

### Summary

- **Superclass-Subclass Relationship**: Use `rdfs:subClassOf` to define a class hierarchy where one class is a subclass of another.
- **Metaclass-Instance Relationship**: Use `rdfs:type` on classes to define that a class is an instance of a metaclass, establishing a higher-level classification.
  - t.2024.08.23.23 aka [[t.km.ontology.multi-level-theory]]
These examples should help clarify how to use `rdfs:subClassOf` and `rdfs:type` on classes in RDF using the Turtle syntax.

