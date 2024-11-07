---
id: ln3aog5nvpjjtcywy2lyf8k
title: 2024 11 05
desc: ''
updated: 1730866383694
created: 1730852219138
---


```turtle
@prefix sflo: <https://semanticflow.org/ontology#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

### Classes
sflo:SFRootRepo a owl:Class ;
    rdfs:label "SF Root Repository" ;
    rdfs:comment "The central repository hosting the Semantic Flow project. Can be a root (username/org pages) or a secondary repository." .

sflo:Namespace a owl:Class ;
    rdfs:label "Namespace" ;
    rdfs:comment "Represents an IRI namespace managed within the SFRootRepo." .

sflo:SFNamespaceRepo a owl:Class ;
    rdfs:label "SF Namespace Repository" ;
    rdfs:comment "A repository that manages a specific namespace within the SFRootRepo, preventing overlap and ensuring unique management of entities." .

sflo:NamedIndividual a owl:Class ;
    rdfs:label "Named Individual" ;
    rdfs:comment "A NamedIndividual instance with a unique identity in a namespace." .

sflo:DatasetSeries a owl:Class ;
    rdfs:label "Dataset Series" ;
    rdfs:comment "Represents a series of datasets over time, enabling versioned management." .

sflo:Distribution a owl:Class ;
    rdfs:label "Distribution" ;
    rdfs:comment "A specific representation (format) of a dataset version." .

sflo:Catalog a owl:Class ;
    rdfs:label "Catalog" ;
    rdfs:comment "Aggregates references to NamedIndividuals, datasets, or namespaces for organization and discoverability." .

sflo:Template a owl:Class ;
    rdfs:label "Template" ;
    rdfs:comment "Holds templates or mappings for generating HTML or RDF views for the static site." .


### Properties
sflo:hasNamespace a owl:ObjectProperty ;
    rdfs:label "has Namespace" ;
    rdfs:domain sflo:SFRootRepo ;
    rdfs:range sflo:Namespace ;
    rdfs:comment "Points to namespaces within the SFRootRepo." .

sflo:hasDocsFolder a owl:ObjectProperty ;
    rdfs:label "has Docs Folder" ;
    rdfs:domain sflo:SFRootRepo ;
    rdfs:comment "Reference to the docs folder containing the generated Semantic Flow site." .

sflo:containsDatasetSeries a owl:ObjectProperty ;
    rdfs:label "contains Dataset Series" ;
    rdfs:domain sflo:Namespace ;
    rdfs:range sflo:DatasetSeries ;
    rdfs:comment "Links to dataset series within the namespace." .

sflo:hasCurrentCatalog a owl:ObjectProperty ;
    rdfs:label "has Current Catalog" ;
    rdfs:domain sflo:Namespace ;
    rdfs:range sflo:Catalog ;
    rdfs:comment "Points to the catalog listing current NamedIndividuals." .

sflo:namesIndividual a owl:ObjectProperty ;
    rdfs:label "names Individual" ;
    rdfs:domain sflo:SFNamespaceRepo ;
    rdfs:range sflo:NamedIndividual ;
    rdfs:comment "Lists NamedIndividuals defined by the namespace repository." .

sflo:hasDatasetSeries a owl:ObjectProperty ;
    rdfs:label "has Dataset Series" ;
    rdfs:domain sflo:NamedIndividual ;
    rdfs:range sflo:DatasetSeries ;
    rdfs:comment "Links to datasets related to the NamedIndividual." .

sflo:hasCurrentVersion a owl:ObjectProperty ;
    rdfs:label "has Current Version" ;
    rdfs:domain sflo:DatasetSeries ;
    rdfs:comment "Points to the latest stable dataset version." .

sflo:hasDistribution a owl:ObjectProperty ;
    rdfs:label "has Distribution" ;
    rdfs:domain sflo:DatasetSeries ;
    rdfs:range sflo:Distribution ;
    rdfs:comment "Points to the various formats (e.g., TTL, JSON-LD) for a dataset." .

sflo:appliesToNamedIndividual a owl:ObjectProperty ;
    rdfs:label "applies To Named Individual" ;
    rdfs:domain sflo:Template ;
    rdfs:range sflo:NamedIndividual ;
    rdfs:comment "Associates the template with a NamedIndividual." .

sflo:mappingRule a owl:DatatypeProperty ;
    rdfs:label "mapping Rule" ;
    rdfs:domain sflo:Template ;
    rdfs:comment "Defines rules for transforming RDF data to HTML." .

sflo:hasCurrentDistribution a owl:ObjectProperty ;
    rdfs:label "has Current Distribution" ;
    rdfs:domain sflo:DatasetSeries ;
    rdfs:range sflo:Distribution ;
    rdfs:comment "Points to the current distribution of a dataset, typically using a consistent '_current' identifier for easy access to the latest state." .

sflo:currentDataset a owl:ObjectProperty ;
    rdfs:label "current Dataset" ;
    rdfs:domain sflo:DatasetSeries ;
    rdfs:range sflo:Distribution ;
    rdfs:comment "Provides a direct link to the '_current' version of the dataset for a given series, ensuring consistent access to the most recent state." .

```