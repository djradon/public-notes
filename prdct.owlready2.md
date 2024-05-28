---
id: cj1ur3kon4dj3wk1e7ixgl1
title: Owlready2
desc: manipulating OWL 2.0 ontologies in Python
updated: 1716920419271
created: 1696270914835
---

- 
- #docs https://owlready2.readthedocs.io/
- written-in: #python
- [[p.supports]] [[prdct.owl]]
- [[p.builtOn]] [[prdct.hermit]]

## Features

-   Import OWL 2.0 ontologies in NTriples, RDF/XML or OWL/XML f
    
-   Export OWL 2.0 ontologies to NTriples or RDF/XML
    
-   Manipulates ontology classes, instances and properties transparently, as if they were normal Python objects
    
-   Add Python methods to ontology classes
    
-   Perform automatic classification of classes and instances, using the HermiT or Pellet reasoner (included)
    
-   Load DBpedia or UMLS (for medical terminology, using the integrated PyMedTermino2 submodule)
    
-   Native support for optimized SPARQL queries
    
-   Tested up to 1 billion of RDF triples! (but can potentially support more)
    
-   In addition, the quadstore is compatible with the RDFlib Python module
    
-   Finally, Owlready2 can also be used as an ORM (Object-Relational mapper) – as a graph/object database, it beats Neo4J, MongoDB, SQLObject and SQLAlchemy in terms of performances