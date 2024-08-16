---
id: lkkkisrk9liyko1av5yoos2
title: Introducing Ontogen
desc: ''
updated: 1723832434998
created: 1723554355082
---

- https://ontogen.io/introduction/part-1, https://ontogen.io/introduction/part-2, 
- written-by: @marcel-otto

## Highlights

### Source Control Management vs. Data Control ManagementPermalink

- Roles: In an SCM, the committer is the crucial role. While SCMs recognize the difference between author and committer, in practice, this is usually of little importance. For a dataset, however, authorship, i.e., the exact source of datasets, is of greater importance, and many other roles are relevant and should be differentiable, such as data processors (people or systems that transform, clean, or enrich raw data), data curators (experts who organize, categorize, and enrich data with metadata), data protection officers, etc.
-   Lack of metadata: Datasets often require extensive metadata (e.g., origin, license, timestamps) that are not natively supported in SCMs.
-   Granularity of changes: SCMs often work at the file level, while for datasets, individual records or fields may be relevant.
-   Database integration: DCMs should ideally be able to interact directly with database systems, which is not provided for in SCMs.

### Problems with previous versioning systems for rdf

- The main problem with named graphs for versioning is that parts of a graph simply cannot be addressed directly.
  - This forces us to create a separate named graph for every small group of triples we want to version, which can quickly lead to a flood of graphs and thus an unwieldy RDF dataset.
  - This becomes particularly problematic when working with different named graphs for content purposes, which then become difficult to distinguish among this flood.
- With RDF-star, "it is now trivial to define virtual, URI-identifiable sets of statements, i.e., partial graphs within a graph" by assigning the statement to a common resource using a property.

### RTC

published the [[prdct.rdf-triple-compounds]] (RTC) vocabulary last year

## RDF Speech Acts

- An og:SpeechAct represents a very specific form of speech act: the utterance of RDF statements or modification.
  - allows us to capture not just the content of RDF data, but also the act of asserting or changing that data, along with all the contextual information that surrounds that act.
  - an action that does not represent the actual addition or modification of the dataset (we will continue to call this action a commit, following the usual versioning terminology)
  - Instead, it represents the act of the original utterance of the statements in this dataset or subsequent acts that supplement, revise, confirm, etc. the original statements. 
    - This is because the central questions of provenance, i.e., the origin of the data, revolve around these acts.
- our aim is to provide a model that allows us to capture information related to all possible questions about these utterances and record them as metadata.
- we don’t need to develop a new ontology from scratch to model these metadata. There is already an excellent and standardized basis: the [[prdct.prov-o]] vocabulary
- we define our og:SpeechActs as a special manifestation, i.e., a subclass of prov:Activity
  - allows us to leverage the extensive semantics of the PROV vocabulary while modelling our specific concept of speech acts for RDF data.

## Propositions

- An og:SpeechAct is thus a prov:Activity that can be associated with triple compounds with different pragmatics via four properties, the so-called action properties
  -   `og:add`: A triple compound, i.e., a set of statements that is simply asserted without any further intentions. When persisted to a dataset in a triple store, these statements should be added.
  -   `og:update`: A triple compound, i.e., a set of statements that is asserted with the intention to overwrite all previous statements with the same subject and predicate. When persisted to a dataset in a triple store, these statements should be added and the existing statements with the same subject and predicate should be overwritten.
  -   `og:replace`: A triple compound, i.e., a set of statements that is asserted with the intention to overwrite all previous statements with the same subject. When persisted to a dataset in a triple store, these statements should be added and the existing statements with the same subject should be overwritten.
  -   `og:remove`: A triple compound, i.e., a set of statements that should be retracted (“negated”). When persisted to a dataset in a triple store, it should remove these statements.
- the action properties do not associate the og:SpeechAct with triple compounds in general, but with og:Propositions, a subclass of rtc:Compound
  - i.e., a special kind of triple compound that should exhibit some particular properties in this versioning context. 
  - We achieve this by using URI-encoded SHA256 hashes of the statement set for the URIs of the og:Propositions.
- This approach allows us to achieve some important properties for our use case.
  - we have a method to automatically generate the URIs of the og:Propositions
  - the authenticity of the statement set of the og:Proposition is verifiable, as we can detect whether the statement set is unchanged
    - Each og:Proposition can be verified by recalculating the hash of its canonicalized triple sets
    - Changes or manipulations to the data would inevitably lead to a change in the hash and thus an inconsistent URI, which would be easily detectable.
  - the og:Propositions exhibit an interesting identity property: propositions with the same set of statements receive the same URI
    - This means that if the og:Proposition statement set appears in different og:SpeechActs, for example, because it was og:added once and og:removed once, the same statement set should not be duplicated a third, fourth, or fifth time, etc., in the rtc:elements of different og:Proposition compounds, but should reference the same og:Proposition.
- Thus, og:Propositions represent immutable, abstract sets of statements that can be used in different, independent contexts and always have the same URI. 
  - one problem: if two og:Proposition statement sets contain blank nodes and differ only in the local names used for the blank nodes, but are otherwise isomorphic, they are actually the same abstract statement set, which should therefore lead to the same URI.
- So, og:Propositions are an abstraction over concrete statement sets: the same statement set in different triple stores, with potentially different blank nodes, are all identified by the same URI of a resource.
  - These og:Proposition compounds are thus, like the propositions of logic, abstract entities that are not bound to any utterance.
  - Only through the utterance within an og:SpeechAct do they become time- and context-bound.
  - As abstract entities, unlike RTC compounds in general, the og:Proposition compounds usually do not contain metadata, as the interesting metadata is utterance-related and therefore belongs to the og:SpeechAct
- The URI of the speech act itself in Ontogen is:
  -   the URI-encoded SHA256 hash of all `og:Proposition`s linked through its action properties (i.e., their SHA256 URIs),
  -   the `prov:endedAtTime` timestamp,
  -   and the `og:speaker` (a subproperty of `prov:wasAssociatedWith`) of the `og:SpeechAct`, or the `og:dataSource` (a subproperty of `prov:used`) if the speaker is unknown.
   
### Example

```turtle
@prefix : <http://example.com/> .
@prefix og: <https://w3id.org/ontogen#> .
@prefix rtc: <https://w3id.org/rtc#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix dc: <http://purl.org/dc/terms/> .

<urn:hash::sha256:b1f9fb63d4cbfcc48c9da35c0526a1aeb394dce9f6fc10368d5ec3d248a8f070>
    a og:SpeechAct ;
    dc:description "Update of Sarah Miller's personal information following her marriage" ;
    og:add <urn:hash::sha256:3e9347bcd3f39fba5afc5a4b2f132bb2468cf399a4dfa6e34f52aea85e755a6e> ;
    og:update <urn:hash::sha256:4d33b032442d54f94052b55643240adf79dbea7ae635c5fb167a124dc3d6444a> ;
    og:speaker :JaneSmith ;
    prov:startedAtTime "2023-07-26T09:30:00Z"^^xsd:dateTime ;
    prov:endedAtTime "2023-07-26T09:31:15Z"^^xsd:dateTime ;
    prov:wasInformedBy :MarriageCertificateSubmission ;
    prov:used :MarriageCertificate20230725  .

<urn:hash::sha256:3e9347bcd3f39fba5afc5a4b2f132bb2468cf399a4dfa6e34f52aea85e755a6e>
    rtc:elements 
        << :employee39 :emailAddress "sarah.johnson@example.com" >>, 
        << :employee39 :marriageDate "2023-07-25"^^xsd:date >> .

<urn:hash::sha256:4d33b032442d54f94052b55643240adf79dbea7ae635c5fb167a124dc3d6444a>
    rtc:elements 
        << :employee39 :familyName "Johnson" >>, 
        << :employee39 :maritalStatus :Married >> .

:JaneSmith a prov:Person ;
    foaf:name "Jane Smith" ;
    foaf:mbox <mailto:jane.smith@example.com> .

:MarriageCertificate20230725 a prov:Entity ;
    dc:title "Marriage Certificate for Sarah Miller and Michael Johnson" ;
    prov:generatedAtTime "2023-07-25"^^xsd:date .

:MarriageCertificateSubmission a prov:Activity ;
    prov:wasAssociatedWith :employee39 ;
    prov:generated :MarriageCertificate2023-07-25 ;
    prov:endedAtTime "2023-07-26T09:00:00Z"^^xsd:dateTime .
```

## Commits

- In Ontogen, commits represent the actual changes made to a repository, resulting from applying an og:SpeechAct to this repository with its existing data.
  - Like an og:SpeechAct, og:Commits are a prov:Activity.
  - However, they represent the act of adding or modifying data in a dataset within a triple store in a specific state, rather than the act of uttering these statements, which may have occurred at a much earlier time and by a different speaker.
- Like an og:SpeechAct, an og:Commit is a structure composed of og:Propositions linked through various action properties.
- However, since they have a slightly different pragmatics here and a different rdfs:domain, different properties and an additional one are used for this purpose.
  - The semantics of this set of properties is characterized by encoding repository-relative changes, i.e., expressing the minimal changes relative to the current state of the dataset.
  - This is crucial to ensure that og:Commits are revertible, as otherwise ambiguities in the history would arise:
    - Can we simply remove every statement added by a commit from the triple store during a revert?
    - The same applies to removals of statements that do not actually exist in the current dataset and therefore should not be restored during a revert.
    - Additionally, the specific statements implicitly deleted by og:updates and og:replace must be explicitly recorded in an additional proposition so that they can be restored during a revert.
- To ensure the reversibility of commits, the internally so-called “effective changeset” must be determined.
- From this, corresponding propositions are then generated and linked to the og:Commit via the following action properties, along with the og:SpeechAct that this commit reproduces on the repository:
  -   `og:committedAdd`, `og:committedRemove`, `og:committedUpdate`, `og:committedReplace`: These action properties represent the minimal sets of statements as propositions necessary to change the state of the repository to match the corresponding `og:Proposition`s of the `og:SpeechAct`. They contain only the actually required changes.
  -   `og:committedOverwrite`: This property contains a set of statements as a proposition that represents the statements to be implicitly deleted due to updates or replacements.
- If none of the changes conflict with existing triples (or in the case of deletions, with non-existing triples) in the triple store, the og:Propositions of the og:Commit are the same as the og:Propositions in the og:SpeechAct and do not require additional space for dedicated modified og:Propositions.
- Theoretically, we could rely on two simple sets for additions and deletions to determine the statement sets of the effective changes. However, to increase the chance of reusability of og:Propositions, we continue to use the same actions for commits, so that only in case of overlap with existing data, a separate, dedicated og:Proposition for the commit must exist.
- a commit is, of course, like in other version control systems, a sequential, uni-directionally linked list of commits to the respective predecessor commits.
  - The predecessor commit is defined in Ontogen via the og:parentCommit property.
- The automatically generatable identifiers of an `og:Commit` are, like those of `og:SpeechAct`s and `og:Proposition`s, again URI-encoded SHA256 hashes, in this case of:
  -   the hash URI of the parent commit
  -   the hash URIs of the propositions of the commit
  -   the URI of the committer
  -   the timestamp of the commit
  -   and the commit message

## Ontogen’s Repository and Service Model

### Isolated history graph

- A distinctive feature of storing versioning information in Ontogen is the strict separation between the actual data and the versioning artifacts.
  - **Ontogen stores all versioning information in a separate graph, the so-called og:History graph.**
  - this history graph stores the proposition compounds with the RDF-star statements and the assertions of all higher-level resources such as speech acts and commits.
  - This approach ensures that the actual data of the RDF dataset remains completely free of version control artifacts.
  - The implementation is achieved through the use of RDF-star and the RTC vocabulary. 
    - We use the inverse rtc:elements property of the rtc:elementOf property and store the RDF-star assertions as “unasserted” in the history graph.
  - the current version of Ontogen only supports versioning of individual RDF graphs. Managing changes across different graphs of an RDF dataset is planned for future versions.

### Ontogen repositories as DCAT catalogs

- [[prdct.rdf.dcat-data-catalog-vocabulary]] is suitable:
  -   Flexibility and extensibility: DCAT provides a basic vocabulary that can be easily adapted and extended to specific needs.
  -   Hierarchical structuring: DCAT allows the modeling of nested catalog structures, which is ideal for organizing complex RDF datasets.
  -   Comprehensive metadata: DCAT offers a rich set of properties for describing datasets, including license information, access rights, and temporal aspects, some of which can even be provided automatically in the context of Ontogen, as these can be derived from the speech act and commit history (authors, creation period, data sources, etc.)
  -   Support for versioning and integration with PROV: The soon-to-be-completed version 3 of DCAT introduces a comprehensive [versioning concept](https://www.w3.org/TR/vocab-dcat-3/#dataset-versions) that is particularly relevant for Ontogen’s use case. This extension also seamlessly integrates the PROV vocabulary, which forms the basis for Ontogen’s RDF speech act and commit history. This integration enables the direct derivation and modeling of provenance information and version metadata from the version history. For example, authors, creation dates, and other relevant metadata for specific revisions of a dataset can be automatically generated and presented in a standardized form. This close intertwining of versioning and provenance tracking makes DCAT 3 an ideal vocabulary for metadata description in Ontogen, as it can precisely map the complex temporal and authorial aspects of versioned RDF datasets.
  -   Standardization and interoperability: As a W3C standard, DCAT enjoys wide acceptance and support in the data management community. This promotes Ontogen’s compatibility with other systems and tools in the field of data management. For example, DCAT has gained great importance in the European Union, where it serves as the basis for DCAT-AP (DCAT Application Profile for data portals in Europe) and is supported in prominent data catalog platforms. The use of DCAT in Ontogen thus allows seamless integration into existing data ecosystems and facilitates the exchange of metadata with a variety of platforms and services.
- we define an og:Dataset as a subclass of dcat:Dataset. In fact, we can define it even more specifically as a subclass of dcat:Catalog, because according to the above broader definition, one can also consider a single graph of an RDF dataset as a dcat:Dataset and thus define it as a collection of these.
- we define an `og:Repository` as a DCAT catalog around such an og:Dataset, supplementing it with two additional entries, so that an og:Repository as a DCAT catalog consists of exactly two explicit DCAT dataset entries and one implicit graph:
  -   One entry for the `og:Dataset` DCAT catalog with the pure user-defined graphs (which is defined using the `og:repositoryDataset` property, a sub-property of `dcat:dataset`).
  -   One entry for the `og:History` graph with the provenance history of the speech acts and commits as PROV activities, including the linked PROV entities and PROV agents (which is defined using the `og:repositoryHistory` property, a sub-property of `dcat:dataset`).
  -   A repository graph that contains the DCAT metadata description of the `og:Repository` itself, including the DCAT metadata description of the `og:Dataset` catalog. This graph poses a particular challenge as it is both part of the repository and its description. This self-referencing leads to a conceptual ambiguity: on the one hand, the graph is a `dcat:Dataset`, on the other hand, it contains the description of the entire repository including itself. In the current DCAT specification, there is no clear solution for this problem of self-description as an explicit part of a `dcat:Catalog`. Therefore, in the current version of Ontogen, this graph is treated implicitly as part of the definition of an `og:Repository`, without an explicit `dcat:dataset` entry for it in the catalog. This solution is pragmatic, but ultimately not really satisfactory. Better suggestions for solving this problem would be very welcome.

### Ontogen instances as DCAT services

- An `og:Service`, which is defined as a subclass of dcat:DataService, is a resource that structurally consists of two elements:
  -   The `og:Repository` linked via the `dcat:servesDataset` sub-property `og:serviceRepository`
  -   An `og:Store` linked via the property `og:serviceStore`, which represents the locally running SPARQL triple store in which the repository is stored
-   While the same Ontogen repository can exist on different computers, the various Ontogen instances on these computers operate as different Ontogen services with different stores but the same repository.

## Ontogen Configuration with Bog

- [[prdct.bog]] has `bog:ref`, whereby a blank-node resource can be given a locally-valid name

```turtle
# we omit this prefix in the following code snippets
@prefix : <https://w3id.org/bog#> .

[ :ref "this-service-instance" ; a og:Service ] .
```
  - When first interpreted by the Bog interpreter, this is interpreted as minting a new, locally named resource. A random salt is then stored in a file with the specified name.
  - The interpreter then replaces the blank node with a generated UUIDv5 URI
  - For each subsequent interpretation, loading the salt reproduces exactly the same UUIDv5 URI, allowing for consistent translation to the same graph.
- Bog offers another solution to avoid name changes: the indexical `bog:this` property.
  - The concept of [[t.phil.language.indexicality]] comes from the philosophy of language and refers to linguistic expressions whose meaning depends on the context of their utterance.
  - It allows referencing individual instances of classes that represent a unique individual relative to this instance in the context of the executing instance.
  - Consequently, these quasi-relative singletons can also be referenced directly via their class in the context of the executing instance.

### Example

- In the context of execution on an Ontogen instance, there is exactly one distinguished individual of the class `og:Service` that represents this very instance as an `og:Service`. Thus, in Bog, it can also be referenced using the `bog:this` property as follows:

```turtle
[ :this og:Service ] .
```

- This is interpreted by the Bog interpreter as follows:

```turtle
[ :ref "service" ; a og:Service ] .
```

### Bog Future

- It is planned to spin off Bog as its own project with expanded functionality in the next version of Ontogen. In particular, it should be possible to give the resources managed with Bog proper Linked Data URIs at a later point in time if needed. ^ezq1fl2ro8qr

## Store Adapters

- triple store adapters are implemented as subclasses of og:Store
  - This solution is not only conceptually very simple but also provides a comprehensive basis for solving this problem thanks to [[prdct.grax]] and its support for polymorphic links
    - (In particular, we overcome the [“Walled Gardens within Elixir”](https://marcelotto.medium.com/the-walled-gardens-within-elixir-d0507a568015), which potentially allows store adapters to be developed and versioned as separate Hex packages if their complexity should increase over time, which might happen quickly when triple store-specific extensions are implemented in a store adapter.)


## References

- https://ontogen.io/introduction/part-2