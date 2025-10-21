---
id: bgo1umvoasmlbvq3cie4hzj
title: An Extensible Approach to Multi Level Ontology Modelling
desc: 'explicating property inheritance and materializing (continuously) via SPARQL inserts'
updated: 1757612161194
created: 1725511917090
---

- https://www.scitepress.org/PublishedPapers/2021/106842/106842.pdf
- topics: [[t.km.ontology.multi-level-theory]] 

## Thoughts

- If you have to run SPARQL queries continuously, you might as well just add the information to the model explicitly

## Highlights

### Introduction

- in the Vertebrate Taxonomy Ontology (VTO) (Phenoscape, 2021) and the NCBI Taxonomy (NCBI, 2021), all biological species are modelled as classes
- In contrast, in the Wildlife Ontology (WO) (BBC, 2021) and in the Global Biodiversity Information Facility (GBIF, 2021), biological species are modelled as instances.
  - The authors of the WO state on (BBC, 2021): “One perennial problem associated with modelling biological taxonomies using RDF is whether to attempt to model individual species as classes, or whether to simply model species as instances of a generic Species class. The latter approach is simpler and avoids creating a huge ontology that attempts to model all biological organisms. Existing ontologies have taken different approaches to resolving this issue, some choosing one style, others another. At present there doesn’t seem to be a consensus. With this in mind, the Wildlife Ontology adopts the simpler of the two approaches, i.e. modelling species as instances of a Species class, as this maximises interoperability with many of the existing Linked Data sources, particularly dbpedia, which adopt similar approaches.”
- **The contribution of this paper is a modelling approach which rigorously utilizes multi-facet (Atkinson and Kühne, 2001; Neumayr et al., 2009; Frank, 2014) behaviour, an aspect of multi-level modelling, allowing entities to be modelled as classes (class facet) and instances (instance facet) simultaneously**

### Related Work

- classes are described as groups of resources and instances as their members. 
- @dean-allemang calls the reaction of defining everything as classes "rampant classism"
  - "We agree with them"
- (Noy and McGuinness, 2021) [[ar.ontology-development-101-a-guide-to-creating-your-first-ontology]]: A criterium they define for the decision to model something as a class or an instance is the lowest level of granularity in the representation.
  - i.e., individual instances are the most specific concepts represented in a knowledge base
- various authors recommend modelling pairs of classes where a class is associated with a corresponding type class
  - modelling pattern is called materialization pattern ^pvldw3ag53on
  - the term powertype is used in (Odell, 1994) and (Guizzardi, et al., 2015). ^vt540o589i6g
- With conventional modelling approaches it is not possible to mix the properties of base class and its powertype into one class, since it makes no sense to have a property Number_Plate for a Car_Model.
- **Our approach is simpler insofar as it does not require separate entities Car and Car Model while still explicitly distinguishing between the different facets.**
- Another approach to avoid separate entities Car and Car Model is described in (Neumayr et al. 2009), called Multi-Level Domain Modeling. Properties are annotated with meta attributes which define rules for inheritance and instantiation. E.g. for the base class Car the data property maxSpeed is annotated with :model to refer to a Car_Model while the data property Milage is annotated with :physical_entity to refer to an individual car. This allows merging the properties of Car and Car_Model into only one class Car while keeping the semantics of the properties clear.
- In a comparable approach (Frank, 2014), level numbers are assigned to properties. For Car the property Milage would be defined with level=0 which corresponds to the :physical_entity annotation in (Neumayr et al. 2009), while maxSpeed would be annotated with level=1 which corresponds to the :model annotation. Annotating properties with multiple levels or with different levels for different contexts is not possible, as is enabled in our approach.
- In (Brasileiro et al., 2016a), a fixed separation of entities into individuals, 1 st order type, 2 nd order type and 3 rd order type is proposed. Our approach is more flexible as it allows context-dependent viewpoints.
- Multi-facet behaviour as used in (Neumayr et al., 2009) may regard entities as classes and instances simultaneously, where needed. 
  - In contrast, OWL 1 DL requires a strict separation between the classes and individuals (W3C, 2012). Insofar, multi-facet behaviour is not compatible with OWL1 DL. 
  - OWL 2 DL relaxes this separation somewhat to allow different uses of the same term which is called [[t.cs.semantic-web.punning]]. 
    -  “e.g., Eagle, to be used for both a class, the class of all Eagles, and an individual, the individual representing the species Eagle belonging to the (meta)class of all plant and animal species”. 
    - However, OWL 2 DL still imposes certain restrictions, e.g., a name can only be used for one kind of property (W3C, 2012).

### Example: Animal Ontology

- based on [[prdct.wildlife-ontology-wo]] but adds [[prdct.skos]]
- we favour a simple modelling approach modelling concrete species like polar bear as instances. 
- We use the object property skos:broader to specify
the biological taxonomy,
- concrete taxons are attributed with
properties, e.g.:
```turtle
:Polar_Bear skos:altLabel "Ursus maritimus" .
```

### Multi-Facet Behaviour

![[t.cs.semantic-web.class#^6ij3g83vefyj]]
- In RDF/RDFS it is not forbidden to specify an entity as an instance of something which has not been specified as a class. Although this is syntactically correct, we consider this a modelling flaw.
- It is also allowed to model something as a class and an instance simultaneously. Every class is an example of this pattern since every class is an instance of rdfs:Class. Also rdfs:Class is an example of this since it is a class and additionally an instance of itself.
  - In (Atkinson and Kühne, 2001) and (Neumayr et al., 2009) this is called multi-facet. 
  - It is argued that this may considerably reduce unnecessary complexity in ontologies with multiple levels. 
  - We agree with them and use the multi-facet behaviour to add capabilities to ontologies like AO incrementally when required by new use cases.

### Property Types

- Datatype properties as well as object properties always relate to the instance facet of an entity
- Does the fact that the species polar bear is vulnerable mean that the individual polar bear Knut is vulnerable? No
```turtle
:Bears :habitat :Terrestrial_habitat.
:Terrestrial_habitat a :Habitat.
:Habitat a rdfs:Class.
```
- Again, this information relates to the instance facet of the biological family of bears.
  - Does this information also apply to all genus and species of the family bears? Yes
  - And how about individual animals like Knut? Yes
- [although] both properties :conservation_status and :habitat relate to the instance facet, they are semantically different.
  - The difference is how information can be inferred between the facets along hierarchies within the facets.
    - this semantic difference is independent of the distinction between object properties and datatype properties

### Inheritance

- for inferring information between facets as well as along hierarchies within facets
  - e.g., rdfs:subClassOf hierarchies within the class facet or skos:broader hierarchies within the instance facet.
  - In our example, the hierarchy between taxons is specified by the object property skos:broader

```turtle
:Polar_Bear a :Species; skos:broader :Bear.
:Bear a :Genus; skos:broader :Bears.
:Bears a :Family; skos:broader :Carnivores.
:Carnivores a :Order; skos:broader :Mammals.
:Mammals a :Class; skos:broader :Chordates.
:Chordates a :Phylum; skos:broader :Animals.
:Animals a :Kingdom.
```

  - t.2024.09.23.15 confusing 
    - why not `:Bear subClassOf :Bears` too
    - why not `:Species skos:broader :Genus` 
  - t.2025.09.11.10 maybe...
    - we're talking about using broader/narrower so we don't have to worry about the OWL 2 DL restrictions
    - you could also have taxons represented as individuals.

#### Sample Properties

1. :birth_date "2006-12-05" refers to an
instance of a concrete species, e.g., :Knut,
only.
2. :population 31000 refers to a concrete
species, genus, family etc., e.g.,
:polar_bear, but cannot be inherited from
broader to narrower taxons, and not to their
instances.
3. :conservation_status : vulnerable
refers to a concrete taxon, e.g., the species
:polar_bear. If a conservation status would
be specified for an entire genus or family then
it could be inferred that all species belonging
to this genus or family have the same
conservation status, hence can be inherited
along the skos:broader hierarchy.
However, it cannot be inherited to instances of
concrete species like :Knut.
4. :habitat :Terrestrial_habitat refers
to a concrete species, genus, family etc., e.g.,
:Bears, it can be inherited along the
skos:broader hierarchy, e.g., from :Bears
to :Bear and from :Bear to :Polar_bear.
Additionally, it can be inherited from concrete
species like :Polar_Bear to instances of this
species like :Knut.

#### Property Behaviour Explication

- in order to use inferencing for implementing inheritance behaviour, it is necessary to explicate the intended behaviour of properties like :birth_date, :population, :conservation_status, and :habitat. 

```turtle
:conservation_status a rdfs:Property,
:BroaderInheritedProperty.
:habitat a rdfs:Property,
:BroaderInheritedProperty,
:TypeInheritedProperty
```

- :conservation_status and :habitat are of type :BroaderInheritedProperty in order to express that those properties can be inherited along the skos:broader hierarchy from broader to narrower taxons. 
- Additionally, :habitat is of type :TypeInheritedProperty in order to express that this property can additionally be inherited along the rdf:type relationship from classes to their instances.
- so four possibilities, plus can apply to Object properties and Datatype properties

### Querying and Inferencing

```SPARQL
SELECT *
WHERE{:Knut ?p ?o.}
```

- will not contain any information about Knut’s habitat.
- Likewise, a similar query for all information about the species polar bear will return all predicates and objects explicitly specified for the subject :Polar_Bear like :population 31000, but no information about the habitat of polar bears.
  - because habitat information is specified for a broader taxon, here the family of bears.


#### inheriting properties along skos:broader hierarchies

```SPARQL
INSERT {?s ?p ?o.}
WHERE {?p a :BroaderInheritedProperty.
?s skos:broader* ?b.
?b ?p ?o.}
```

- This rule applies for RDF triples with predicates ?p that have been specified of type :BroaderInheritedProperty like, e.g., :conservation_status or :habitat.
- If a subject ?s is in a transitive skos:broader relationship to some other subject `?b` then all triples with predicate ?p and object ?o can be inherited for subject ?s 
- Executing this SPARQL INSERT statement materializes the inferencing results in the ontology

#### inheriting properties from classes to instances

```SPARQL
INSERT {?s ?p ?o.}
WHERE {?p a :TypeInheritedProperty.
?s a ?c.
?c ?p ?o.}
```

- This rule applies for RDF triples with predicates ?p that have been specified of type :TypeInheritedProperty like, e.g., :habitat.
- If a subject ?s is in a rdf:type relationship to some class ?c then all triples with predicate ?p and object ?o can be inherited for subject ?s .

#### Notes

- in practice, all rules have to be executed repeatedly until no rule fires any more, as is common in forward-chaining rule-based systems.
- We have deliberately chosen an informal property like skos:broader for the AO in order to demonstrate how semantics for different use case contexts may be added incrementally, independently of the modelling style of the initial ontology
  - If a more formally specified relationship like rdfs:subClassOf is deemed necessary in a certain use case context then a SPARQL rule for inferring rdfs:subClassOf relationships from skos:broader relationships may easily be added.

### Discussion

- rigorously utilizing the multi-facet behaviour for modelling ontologies supports simplicity, expressiveness, modularity, extensibility and flexibility.
- Utilizing the multi-facet behaviour is more concise than using the materialization pattern
- multi-facet behaviour could impede OWL DL reasoning
- In (Frank, 2014), inheritance is restricted to the definition of properties, i.e., using a property specified in a higher-level object in a lower level. Inferring property values between facets (?) and along hierarchies within facets, e.g., rdfs:subClassOf or skos:broader, is not discussed.

## References

- [[book.practical-ontologies-for-information-professionals]]