---
id: bp4xf4smzbtvrq14zbt1vwf
title: Linked Data and Time Modeling Researcher Life Lines by Events
desc: ''
updated: 1724998833711
created: 1724994896253
---

- https://www.researchgate.net/publication/257230986_Linked_Data_and_Time_-_Modeling_Researcher_Life_Lines_by_Events
- authors: @johannes-trame @carsten-kessler @werner-kuhn
- topics: [[t.km.knowledge-representation]] [[t.cs.semantic-web.temporal]] [[t.cs.sd.event-modeling]] [[prdct.dolce.dns-ultralite]]

## Highlights

### Introduction

- We propose to build on the event participation pattern from the well founded DOLCE+DnS Ultralite Ontology (DUL)
- Modeling the act of publishing as an event and separating it from the resulting publication as an information object provides us with a sound basis for temporal reasoning

### Time in Knowledge Representation

- [[t.cs.web.w3c.rdf.open-world-assumption]] and [[t.cs.web.w3c.rdf.monotonicity]] "make the modeling of time-dependent relationships challenging"
- [[t.km.reification]] and [[t.cs.web.w3c.rdf.named-graphs]] have been proposed
- RDF reification is one of the most confusing and controversial constructs in the RDF specification, also since its meaning differs from the meaning of reification in conceptual modeling (representing n-ary relationships through binary ones) or
linguistics (turning a verb into noun) ^yyu4yq3zuw4f
- Named graphs provide a lightweight but useful extension of the initial design encoding and query languages. Named graphs are widely accepted by the community to provide provenance information and they have been incorporated into the W3C recommendation for SPARQL 1.1.5 Since named graphs are formally subgraphs, they have a clearer syntax and semantics. They are easier to handle and more widely supported by software tools than RDF reification. However, as pointed out by Carroll et al. [6] the semantics are intentionally limited and conform to the basic interpretation of RDF(S) in favor of simplicity. Named graphs are explicitly designed to ease the handling of collections of statements and to attach meta information to those collections, such as provenance or licensing information.
- In summary, both RDF reification and named graphs can in principle be used to handle temporally varying information by attaching timestamps to single statements [24] or to (sub)graphs [40]. However, as the temporal dimension stays on a meta-level, it has no implication for the model theoretical interpretation and its existence cannot be stated in the vocabulary. 
  - **therefore, named graphs should only be used for temporal information belonging to the meta level, such as provenance data.**

#### Extensions of RDF(S)

- Since both approaches to time are similar to traditional database techniques (time-stamping or temporal versioning), many researchers have taken up that di- rection, trying to provide a model-theoretic account of time. Within the database community, extensive research has been conducted on two notions of time: valid time (when a change occurred in the real world) and transaction time (when a change was entered to the database) [22]. Various proposals adapting the notion of valid time have been made by the Linked Data community, such as tem- poral RDF graphs (temporal reification vocabulary) [16, 15], multidimensional RDF (extended triple notion) [10], applied temporal RDF (named graphs) [43], stRDF (temporal quad) [25], RDF SpatialTemporalThematic (based on tempo- ral graphs) [34], and temporal quintuples [26].
- These approaches have in common that they either extend the RDF syntax or abuse RDF reification or the context quad in order to “label” a triple with a timestamp. The temporal label is then given a model theoretic interpretation modifying the truth value of the statement. This is done by extending the basic entailment rules of RDF(S) or even by moving to a different logic. However, these approaches are in many respects debatable, as they treat the representation of time as a feature of the encoding language. It is unlikely that all existing software implementations will adapt such syntactic and model theoretic extensions. Moreover, time-stamping triples provides no means to share the underlying conceptual model. We can only see changes between different versions, but we fail to explain where these changes in the real world come from. Finally, it is not clear how the notion of valid time interacts with the Open World Assumption, which supports contradicting statements.

#### n-ary relations

- The natural way to deal with the restriction of binary relations in modeling languages is to use the n-ary design pattern. This approach is also known as conceptual reification of binary relations.
- The basic idea is to turn a property into a class and link it to the existing classes via two additional properties. Figure 2 shows an example suggested by the organization ontology.6 From a practical point of view, n-ary patterns have been criticized because they increase the number of statements and lead to a proliferation of objects. Additionally, the introduction of new (anonymous) individuals through reified relationships causes a maintenance problem and limits the usefulness of RDF and OWL constructs such as domain and range restrictions or inverse property definitions.
- The biggest problem, however, is that the potential application scope of the logical n-ary pattern is very broad. The n-ary pattern is often considered as an ad-hoc workaround and thus it is frequently used in an arbitrary fashion, lacking any design rationale.


### Foundational Ontologies: Objects and Events

- With its cognitive bias [31], the Descriptive Ontology for Linguistic and Cognitive Engineering7 (DOLCE), fits the need of the Semantic Web as a frame of reference for building domain ontologies [9]. It organizes particulars and axiomatizes them according to a set of meta-properties [14]. While DOLCE is relatively complex in its full extent, lightweight versions are provided and can be extended in a modular fashion, for example DOLCE-Lite-Plus7 or DOLCE+DnS Ultralite (DUL).

#### Linguistic view on time

- Linguists face the problem of how to capture adverbial modifiers (locative, temporal or instrumental) of action sentences in logic. Sentences such as “Johannes wrote a paper with a pen in the library at midnight” result in predi- cates of higher arity, such as write(Johannes,a paper,a pen, the library, midnight), where the number of adjuncts for the predicate can become very large
- As a solution to this variable polyadicity problem of action modifiers, Davidson [7] proposed that action predicates should explicitly range over an ad- ditional, normally hidden, event argument: ∃e [write(Johannes,a paper,e) ∧ with(e,pen) ∧ in(e,library) ∧ at(e,midnight)]. 
  - This event argument can then be existentially quantified and bound to the whole sentence, whereas each adjunct will be attached as a separate conjunction clause, thus allowing for an arbitrary number of adjuncts.
  - Parsons [33] advocated to treat the event argument as the only argument of the predicate and link it with a set of thematic roles.
    - Following the proposal by Parson, the structure of our example can be “. . . replaced by a truly compositional theory of predicates whose fundamental notion is that of event participant and whose fundamental predicates are [thematic roles]” [21, p.444]: ∃e [write(e) ∧ agent(e,Johannes) ∧ location(e,library) ∧ time(e, midnight)].
  - The decomposition enables one to represent temporal relations directly in first order structures and to reason over them without the need to move, for example, to a temporal or modal logic

#### Ontological Event Theories

- A dualistic view, where objects and events complement each other [41], is re- flected in most upper-level ontologies such as the Basic Formal Ontology (BFO)8 or DOLCE [31].
- Objects get then located in time through their participation relation in events and events get located in space through their physical participants.
  - Spatial characteristics have an important func- tion for identifying physical objects as well as for defining their unity criteria. 
  - Temporal characteristics play the same role for events
- Roles, in particular, depend on events to come into existence. They carry identity criteria, but do not supply them. 
  - neglecting this may lead to the so-called isA-overloading, for example, placing a concept Employee under Person in the taxonomy)
- Extensive work on the representation of roles has been done by Steimann [42], who presented a list of fifteen different features that may apply to roles. 
  - In this list, @claudio-masolo et al. [32, pp.269–270] identified five characteristics
that refer to the dynamic and temporal nature of roles:
(1) an object can play different roles at the same time
(2) an object can change its roles
(3) an object can play the same role for multiple times simultaneously
(4) some roles can be played by different objects, at the same or different times
(5) some roles can only be played by an object depending on the previous roles
it played
- Masolo et al. [32] argue that the problem with a contextual approach is that the notion of context is still quite fuzzy on its own and one contextual approach may subsume the other. 
  -  Consequently, they suggest to reify roles and separate them from their specification which accounts for the relational and contextual nature of roles. 
  -  This pattern rests on the so called Descriptions and Situations (DnS) extension of DOLCE and is also part of the DUL library.
-  

### Career Trajectories - Events and Roles

- Event ontologies have gained attention in recent years. Examples include [[prdct.cidoc-crm]] [8], the [[prdct.abc-ontology]] [27] or the CultureSampo project [36], where event- based modeling approaches have proven useful to establish a common conceptual reference frame across applications. 
- the [[prdct.event-ontology]] (EO)9 aims for more generic event modeling pattern
- The authors of the [[prdct.lode-ontology]], which provides a mapping between different event models, provide a good overview of the differences [39].
- While LODE and EO do not account for roles, CIDOC CRM [1] realizes roles as properties over properties which cannot be implemented in RDF
- Most recently, the [[prdct.simple-event-model-ontology]] (SEM) [18] has been proposed, as a light-weight model that is neutral with respect to semantic commitments.
  - However, all concepts and relations in SEM are undefined primitives that are only informally and weakly specified.  ^hfr5g0mqkqkk
- we chose [[prdct.dolce.dns-ultralite]]
  - DUL provides a good combination of flexibility and expressiveness and makes at least the basic distinctions explicit, such as that between events, physical objects and social construction ^y3piqf56xjis
  - Our approach is similar to the [[prdct.event-model-f]] [37] which also builds on DUL and provides a number of specialized instantiations of descriptions and situations (DnS).
    -  "By introducing certain types of events and situations, events can be composed to form more complex situations, such as mereological composi- tions of events or causality relations among events." ^uh1jn8phbw3o
    - "the F-Event model does not suggest how to distinguish among different kinds of participants in an event." ^le51vrhfwetp

### Basic Design Decisions and Alignment to DOLCE+DnS Ultralite

#### Events

- Events unfold over time, which means that they can be located directly in a temporal region.
  - in DUL, the region values can be directly added to the Event using the hasEventDate property, or the temporal region, such as a TimeInterval, can be separated from the Event and linked via the property isObservableAt, which is a sub-property of hasRegion.
    - While the former approach is simple on the query and application level, the latter provides a “cleaner” and more flexible solution in representing time values from other calendars
    - **by representing the interval explicitly, the model could be extended to account for fuzzy temporal intervals** ^2zha3u1eje6w
- Since the isObservableAt property in DUL is in the domain of Entity (Objects, Events, Qualities, Abstracts), we introduce a new sub-property eventTime, explicitly linking the Event to its region TimeInterval
  - In order to link the TimeInterval to its region values we introduce the properties hasIntervalStartDate and hasIntervalEndDate ranging over values from the XML date schema.
    - Both are specializations of the hasIntervalDate and hasRegionDataValue property in DUL
- Concerning the classification of events, we take a pragmatic approach and link the Event to an EventType which is a subclass of Concept.
- Since the property isClassifiedBy is the domain of all entities, we introduce a new sub-property eventType with a domain constraint on Event and range constraint on EventTypes
  - This allows us to dynamically type event concepts from external vocabularies as EventTypes.

#### Participation in Events

- A NaturalPerson in DUL belongs to the category of agentive physical objects because they have intentionality and a proper space region.
- We specialize the involvesAgent property of DUL by introducing a new property involvesPerson, with domain constraints on Event and range constraints on NaturalPerson
- 