---
id: 4mertdorsdyo6uq223ssgaq
title: 2024 10 11
desc: 'too gufo'
updated: 1729312196432
created: 1728675519071
---

```turtle
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix kosm: <https://kosmion.github.io/ont/v0/> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix gufo: <http://purl.org/nemo/gufo#> .

# Ontology metadata
<https://kosmion.github.io/ont/v0/kosmion-v0.ttl> a owl:Ontology ;
    rdfs:label "Kosmion ontology" ;
    rdfs:comment "A foundational ontology for modeling relators, relationships, and temporal aspects." ;
    owl:versionInfo "v0.1" ;
    owl:versionIRI <https://kosmion.github.io/ont/v0/kosmion-v0.0.1.ttl> ;
    owl:imports <http://www.w3.org/2002/07/owl#> .

# Define the relator class
kosm:relator a owl:Class ;
    rdfs:label "relator" ;
    rdfs:comment "A class representing relators, which describe relationships (including unary relationships) among entities." .

# Define the context class
kosm:context a owl:Class ;
    rdfs:label "context" ;
    rdfs:comment "A class representing the applicable reality for the relationship represented by a relator." .

# Define the type class, same as gUFO Type
kosm:type a owl:Class ;
    owl:equivalentClass gufo:Type ;
    rdfs:label "type" ;
    rdfs:comment "A class representing types, equivalent to gUFO Type." .

# Define relationship-type class as a subclass of type
kosm:relationship-type a owl:Class ;
    rdfs:subClassOf kosm:type ;
    rdfs:label "relationship type" ;
    rdfs:comment "A class representing types of relationships." .

# Define comparative-relationship-type as a subclass of relationship-type
kosm:comparative-relationship-type a owl:Class ;
    rdfs:subClassOf kosm:relationship-type ;
    rdfs:label "comparative relationship type" ;
    rdfs:comment "A class representing types of comparative relationships." .

# Define material-relationship-type as a subclass of relationship-type
kosm:material-relationship-type a owl:Class ;
    rdfs:subClassOf kosm:relationship-type ;
    rdfs:label "material relationship type" ;
    rdfs:comment "A class representing types of material relationships." .

# Define datatype-relation property
kosm:datatype-relation a owl:DatatypeProperty ;
    rdfs:domain kosm:relator ;
    rdfs:label "datatype relation" ;
    rdfs:comment "A super-property for capturing datatype relations described by a relator." ;

# Define object-relation property as a super-property for relationships described by a relator
kosm:object-relation a owl:ObjectProperty ;
    rdfs:domain kosm:relator ;
    rdfs:label "object relation" ;
    rdfs:comment "A super-property for capturing object relations involved in relationships described by a relator." .

# Define relator-genesis property
kosm:relator-genesis a owl:DatatypeProperty ;
    rdfs:domain kosm:relator ;
    rdfs:range xsd:dateTimeStamp ;
    rdfs:label "relator genesis" ;
    rdfs:comment "The timestamp when the relator was created." .

# Define relator-tombstone property
kosm:relator-tombstone a owl:DatatypeProperty ;
    rdfs:domain kosm:relator ;
    rdfs:range xsd:dateTimeStamp ;
    rdfs:label "relator tombstone" ;
    rdfs:comment "The timestamp when the relator became invalid or ended." .

# Define SHACL constraints
kosm:relator-shape a sh:NodeShape ;
    sh:targetClass kosm:relator ;
    sh:property [
        sh:path kosm:relator-genesis ;
        sh:minCount 1 ;
        sh:maxCount 1 ;
        sh:datatype xsd:dateTimeStamp
    ] ;
    sh:property [
        sh:path kosm:relator-tombstone ;
        sh:maxCount 1 ;
        sh:datatype xsd:dateTimeStamp
    ] ;
    sh:property [
        sh:path kosm:object-relation ;
        sh:minCount 1
    ] .


```