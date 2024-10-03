---
id: nve02n4tp9wrq7ar4wm9kab
title: Cor
desc: ''
updated: 1727995442935
created: 1727995109847
---

```xml

<?xml version="1.0"?>
<!DOCTYPE owl [
  ...
  
<!ENTITY base "http://ontomedia.ecs.soton.ac.uk/ontologies/core/expression">
  ...
]>
<rdf:RDF
	xmlns:rdf="&rdf;"
	xmlns:dct="&dct;">
	<owl:Ontology rdf:about="&base;">
		<rdfs:label>OntoMedia Core</rdfs:label>
		<dc:title xml:lang="en">OntoMedia Core</dc:title>
		<dc:description xml:lang="en">OntoMedia (Ontology for Media) has been designed to describe the interactions occurring in multimedia.</dc:description>
		<dc:creator>Michael O. Jewell (mailto:moj@ecs.soton.ac.uk)</dc:creator>
		<dc:creator>K Faith Lawrence (mailto:kf03r@ecs.soton.ac.uk)</dc:creator>
		<dc:creator>Mischa M Tuffield (mailto:mmt04r@ecs.soton.ac.uk)</dc:creator>
		<dct:created>2005-05-03</dct:created>
		<owl:versionInfo>0.3</owl:versionInfo>
		<owl:imports rdf:resource="http://signage.ecs.soton.ac.uk/ontologies/location" />
	</owl:Ontology>
	<!-- Core -->
	<owl:Class rdf:ID="Expression">
		<rdfs:label>Expression</rdfs:label>
		<rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string">This class represents a piece of information conveyed through a media</rdfs:comment>
	</owl:Class>
	<owl:ObjectProperty rdf:ID="inspired-by">
		<rdfs:label>inspired by</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property indicates that the
expression was inspired by another</rdfs:comment>
		<rdfs:domain rdf:resource="#Expression"/>
		<owl:inverseOf>
			<owl:ObjectProperty rdf:ID="inspired"/>
		</owl:inverseOf>
		<rdfs:range rdf:resource="#Expression"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="has-shadow">
		<rdfs:label>has shadow</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property indicates that the
expression is a variation on another, typically darker in nature</rdfs:comment>
		<owl:inverseOf>
			<owl:ObjectProperty rdf:ID="is-shadow_of"/>
		</owl:inverseOf>
		<rdfs:range rdf:resource="#Expression"/>
		<rdfs:domain rdf:resource="#Expression"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="has-spin-off">
		<rdfs:label>has spin off</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property indicates that the
expression has developed from another</rdfs:comment>
		<rdfs:domain rdf:resource="#Expression"/>
		<owl:inverseOf>
			<owl:ObjectProperty rdf:ID="is-spin-off-of"/>
		</owl:inverseOf>
		<rdfs:range rdf:resource="#Expression"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="is-potentially">
		<rdfs:label>is potentially</rdfs:label>
		<rdfs:range rdf:resource="#Expression"/>
		<rdfs:domain rdf:resource="#Expression"/>
		<rdfs:comment rdf:datatype="&xsd;string">This property indicates that the
expression is potentially another. For example, it may be a possible future
version</rdfs:comment>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="is">
		<rdfs:label>is</rdfs:label>
		<owl:inverseOf>
			<owl:ObjectProperty rdf:ID="is-not">
				<rdfs:comment rdf:datatype="&xsd;string">This property indicates that
the expression is entirely different to another</rdfs:comment>
			</owl:ObjectProperty>
		</owl:inverseOf>
		<rdfs:domain rdf:resource="#Expression"/>
		<rdfs:range rdf:resource="#Expression"/>
		<rdfs:comment rdf:datatype="&xsd;string">This property indicates that the expression is exactly the same as another</rdfs:comment>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="in-context">
		<rdfs:label>in context</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property specifies the context in which this expression lies.</rdfs:comment>
		<owl:inverseOf>
			<owl:ObjectProperty rdf:ID="includes-expression"/>
		</owl:inverseOf>
		<rdfs:range rdf:resource="#Context"/>
		<rdfs:domain rdf:resource="#Expression"/>
	</owl:ObjectProperty>
	<owl:Class rdf:ID="Entity">
		<rdfs:label>Entity</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Expression" />
	</owl:Class>
	<!-- Entity Subclasses -->
	<!-- Items -->
	<owl:Class rdf:ID="Item">
		<rdfs:comment rdf:datatype="&xsd;string">This class represents an entity which may participate in an event within the media. An Item may be abstract or physical</rdfs:comment>
		<rdfs:label>Item</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Entity" />
	</owl:Class>
	<owl:Class rdf:ID="Physical-Item">
		<rdfs:comment rdf:datatype="&xsd;string">This class represents a physical entity
which may participate in an event within the media</rdfs:comment>
		<rdfs:label>Physical Item</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Item" />
	</owl:Class>
	<owl:Class rdf:ID="Abstract-Item">
		<rdfs:comment rdf:datatype="&xsd;string">This class represents an abstract entity
which may participate in an event within the media</rdfs:comment>
		<rdfs:label>Abstract Item</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Item" />
	</owl:Class>
	<!-- Abstract-Item Subclases -->
	<owl:Class rdf:ID="Context">
		<rdfs:comment rdf:datatype="&xsd;string">This class represents the context in
which an event or entity exists</rdfs:comment>
		<rdfs:label>Context</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Abstract-Item" />
	</owl:Class>
	<owl:Class rdf:ID="Collection">
		<rdfs:comment rdf:datatype="&xsd;string">This class represents a collection of
entities</rdfs:comment>
		<rdfs:label>Collection</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Abstract-Item" />
	</owl:Class>
	<!-- Temporal -->
	<owl:Class rdf:ID="Timeline">
		<rdfs:comment rdf:datatype="&xsd;string">This class contains a sequence of occurring
events</rdfs:comment>
		<rdfs:label>Timeline</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Entity" />
	</owl:Class>
	<owl:Class rdf:ID="Occurrence">
		<rdfs:comment rdf:datatype="&xsd;string">This class represents a single occurrence
of an event, placing it at a position in a timeline</rdfs:comment>
		<rdfs:label>Occurrence</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Entity" />
	</owl:Class>
	<owl:ObjectProperty rdf:ID="final-event">
		<rdfs:domain rdf:resource="#Event"/>
		<rdfs:range rdf:resource="http://www.w3.org/2002/07/owl#Class"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="initial-event">
		<rdfs:domain rdf:resource="#Event"/>
		<rdfs:range rdf:resource="http://www.w3.org/2002/07/owl#Class"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="precedes">
		<rdfs:label>precedes</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property defines the occurrence which
immediately follows this occurrence</rdfs:comment>
		<rdfs:range rdf:resource="#Occurence"/>
		<rdfs:domain rdf:resource="#Occurence"/>
		<owl:inverseOf>
			<owl:ObjectProperty rdf:ID="follows"/>
		</owl:inverseOf>
	</owl:ObjectProperty>
	<!-- Events -->
	<owl:Class rdf:ID="Event">
		<rdfs:label>Event</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Expression" />
	</owl:Class>
	<owl:ObjectProperty rdf:ID="has-subject-entity">
		<rdfs:label>has subject entity</rdfs:label>
		<rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string">This property
specifies the entity which carries out the aim of the event</rdfs:comment>
		<rdfs:domain rdf:resource="#Event"/>
		<rdfs:range rdf:resource="#Entity"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="has-object-entity">
		<rdfs:label>has object entity</rdfs:label>
		<rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string">This property
specifies the entity which is the target of the event</rdfs:comment>
		<rdfs:range rdf:resource="#Entity"/>
		<rdfs:domain rdf:resource="#Event"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="has-occurrence">
		<rdfs:label>has occurrence</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property defines any occurrences
of this event</rdfs:comment>
		<rdfs:range rdf:resource="#Occurrence"/>
		<rdfs:domain rdf:resource="#Event" />
		<owl:inverseOf>
			<owl:FunctionalProperty rdf:ID="occurrence-of"/>
		</owl:inverseOf>
	</owl:ObjectProperty>
	<owl:DatatypeProperty rdf:ID="summary">
		<rdfs:label>summary</rdfs:label>
		<rdfs:domain rdf:resource="#Event"/>
		<rdfs:range rdf:resource="&xsd;string"/>
		<rdfs:comment rdf:datatype="&xsd;string">This property is a plain-text description
of what occurs in the event</rdfs:comment>
	</owl:DatatypeProperty>
	<owl:ObjectProperty rdf:ID="precondition">
		<rdfs:label>precondition</rdfs:label>
		<rdfs:range>
			<owl:Class>
				<owl:unionOf rdf:parseType="Collection">
					<owl:Class rdf:about="#Entity"/>
					<owl:Class rdf:about="#Event"/>
				</owl:unionOf>
			</owl:Class>
		</rdfs:range>
		<rdfs:domain rdf:resource="#Event"/>
		<rdfs:comment rdf:datatype="&xsd;string">This property is a state that must exist
before the event can occur</rdfs:comment>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="postcondition">
		<rdfs:label>postcondition</rdfs:label>
		<rdfs:range>
			<owl:Class>
				<owl:unionOf rdf:parseType="Collection">
					<owl:Class rdf:about="#Entity"/>
					<owl:Class rdf:about="#Event"/>
				</owl:unionOf>
			</owl:Class>
		</rdfs:range>
		<rdfs:comment rdf:datatype="&xsd;string">This property contains the state which
should occur as a consequence of this event</rdfs:comment>
		<rdfs:domain rdf:resource="#Event"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="involves">
		<rdfs:label>involves</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property specifies the entities involved
in this event. Note that this includes the subject and object.</rdfs:comment>
		<rdfs:range rdf:resource="#ontomedia_Entity"/>
		<rdfs:domain rdf:resource="#ontomedia_Event"/>
		<owl:inverseOf>
			<owl:ObjectProperty rdf:ID="involved-in" />
		</owl:inverseOf>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="causes">
		<rdfs:label>causes</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property indicates the instigating
factor of an event, whether it be an item, event, or collection.</rdfs:comment>
		<rdfs:range>
			<owl:Class>
				<owl:unionOf rdf:parseType="Collection">
					<owl:Class rdf:about="#Event"/>
					<owl:Class rdf:about="#Entity"/>
				</owl:unionOf>
			</owl:Class>
		</rdfs:range>
		<rdfs:domain>
			<owl:Class>
				<owl:unionOf rdf:parseType="Collection">
					<owl:Class rdf:about="#Event"/>
					<owl:Class rdf:about="#Entity"/>
				</owl:unionOf>
			</owl:Class>
		</rdfs:domain>
		<owl:inverseOf>
			<owl:ObjectProperty rdf:ID="caused_by"/>
		</owl:inverseOf>
	</owl:ObjectProperty>
	<!-- Events Subclasses -->
	<owl:Class rdf:ID="Gain">
		<rdfs:label>Gain</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Event" />
		<rdfs:comment rdf:datatype="&xsd;string">This event class results in an overall
increase of the entities related to the primary subject or subjects of the
event</rdfs:comment>
	</owl:Class>
	<owl:Class rdf:ID="Introduction">
		<rdfs:label>Introduction</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This event class denotes the introduction
of an entity to the media</rdfs:comment>
		<rdfs:subClassOf rdf:resource="#Event" />
	</owl:Class>
	<owl:Class rdf:ID="Loss">
		<rdfs:label>Loss</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This event class results in an overall
reduction of the entities related to the primary subject or subjects of the
event</rdfs:comment>
		<rdfs:subClassOf rdf:resource="#Event" />
	</owl:Class>
	<owl:Class rdf:ID="Transformation">
		<rdfs:comment rdf:datatype="&xsd;string">This event class results in no gain or loss
of attributes or entities, merely alteration</rdfs:comment>
		<rdfs:label>Transformation</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Event" />
	</owl:Class>
	<owl:Class rdf:ID="Action">
		<rdfs:comment rdf:datatype="&xsd;string">This event class describes an action sequence
(ie no plot)</rdfs:comment>
		<rdfs:label>Action</rdfs:label>
		<rdfs:subClassOf rdf:resource="#Event" />
	</owl:Class>
	<owl:ObjectProperty rdf:ID="from">
		<rdfs:label>from</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property specifies the entity which
is being transformed</rdfs:comment>
		<rdfs:range rdf:resource="#Entity"/>
		<rdfs:domain rdf:resource="#Transformation"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="to">
		<rdfs:label>to</rdfs:label>
		<rdfs:comment rdf:datatype="&xsd;string">This property specifies the resultant
entity</rdfs:comment>
		<rdfs:range rdf:resource="#Entity"/>
		<rdfs:domain rdf:resource="#Transformation"/>
	</owl:ObjectProperty>
	<!-- Unsorted -->
	<owl:ObjectProperty rdf:ID="has_parody">
		<rdfs:domain rdf:resource="#Expression"/>
		<rdfs:range rdf:resource="#Expression"/>
		<owl:inverseOf>
			<owl:ObjectProperty rdf:ID="is_parody_of"/>
		</owl:inverseOf>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="occurs">
		<rdfs:range rdf:resource="#locspec_Location_Specifier"/>
		<rdf:type rdf:resource="http://www.w3.org/2002/07/owl#FunctionalProperty"/>
		<rdfs:domain rdf:resource="#Instant_Occurence"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:about="#allows_existance_of">
		<rdfs:domain rdf:resource="#Context"/>
		<owl:inverseOf rdf:resource="#exists_in"/>
		<rdfs:range rdf:resource="#Expression"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="start_point">
		<rdfs:domain rdf:resource="#Period_Occurence"/>
		<rdfs:range rdf:resource="#locspec_Location_Specifier"/>
		<rdf:type rdf:resource="http://www.w3.org/2002/07/owl#FunctionalProperty"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="duration">
		<rdfs:domain rdf:resource="#Period_Occurence"/>
		<rdfs:range>
			<owl:Class>
				<owl:unionOf rdf:parseType="Collection">
					<owl:Class rdf:about="#locspec_Location_Specifier"/>
					<owl:Class rdf:about="#Dimension"/>
				</owl:unionOf>
			</owl:Class>
		</rdfs:range>
		<rdf:type rdf:resource="http://www.w3.org/2002/07/owl#FunctionalProperty"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:about="#contains">
		<owl:inverseOf rdf:resource="#contained_by"/>
		<rdfs:range rdf:resource="#Expression"/>
		<rdfs:domain>
			<owl:Class>
				<owl:unionOf rdf:parseType="Collection">
					<owl:Class rdf:about="#Expression"/>
					<owl:Class rdf:about="#Expression"/>
				</owl:unionOf>
			</owl:Class>
		</rdfs:domain>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:about="#follows">
		<rdfs:range rdf:resource="#Occurence"/>
		<rdfs:domain rdf:resource="#Occurence"/>
		<owl:inverseOf rdf:resource="#precedes"/>
		<rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string">Follows should
specify both timeline and event IDs where there is more than one timeline or over
two events</rdfs:comment>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="timeline_ref">
		<rdfs:range rdf:resource="#Timeline"/>
		<rdfs:domain rdf:resource="#Occurence"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:about="#is_parody_of">
		<rdfs:range rdf:resource="#Expression"/>
		<owl:inverseOf rdf:resource="#has_parody"/>
		<rdfs:domain rdf:resource="#Expression"/>
	</owl:ObjectProperty>
	<owl:ObjectProperty rdf:ID="end_point">
		<rdfs:range rdf:resource="#locspec_Location_Specifier"/>
		<rdfs:domain rdf:resource="#Period_Occurence"/>
		<rdf:type rdf:resource="http://www.w3.org/2002/07/owl#ObjectProperty"/>
	</owl:ObjectProperty>
	<owl:FunctionalProperty rdf:ID="TPQ">
		<rdfs:range rdf:resource="#locspec_Location_Specifier"/>
		<rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string">Terminus Post Quem</rdfs:comment>
		<rdf:type rdf:resource="http://www.w3.org/2002/07/owl#ObjectProperty"/>
		<rdfs:domain rdf:resource="#Occurence"/>
	</owl:FunctionalProperty>
	<owl:FunctionalProperty rdf:ID="type">
		<rdfs:range rdf:resource="http://www.w3.org/2001/XMLSchema#string"/>
		<rdf:type rdf:resource="http://www.w3.org/2002/07/owl#DatatypeProperty"/>
		<rdfs:domain rdf:resource="#Item"/>
	</owl:FunctionalProperty>
	<owl:FunctionalProperty rdf:about="#occurence_of">
		<rdfs:domain rdf:resource="#Occurence"/>
		<rdfs:range rdf:resource="#Expression"/>
		<rdf:type rdf:resource="http://www.w3.org/2002/07/owl#ObjectProperty"/>
		<owl:inverseOf rdf:resource="#has_occurence"/>
	</owl:FunctionalProperty>
	<owl:FunctionalProperty rdf:ID="TAQ">
		<rdfs:domain rdf:resource="#Occurence"/>
		<rdf:type rdf:resource="http://www.w3.org/2002/07/owl#ObjectProperty"/>
		<rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string">Terminus Ante Quem</rdfs:comment>
		<rdfs:range rdf:resource="#locspec_Location_Specifier"/>
	</owl:FunctionalProperty>
	<owl:FunctionalProperty rdf:ID="initial_event">
		<rdfs:comment rdf:datatype="http://www.w3.org/2001/XMLSchema#string">the first event which begins this sequence</rdfs:comment>
		<rdfs:range rdf:resource="#Event"/>
		<rdf:type rdf:resource="http://www.w3.org/2002/07/owl#ObjectProperty"/>
		<rdfs:domain rdf:resource="#Event"/>
	</owl:FunctionalProperty>
</rdf:RDF>
```