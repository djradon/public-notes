---
id: gtdd0u5ibhtg0dri5w6bzg5
title: Kv012
desc: ''
updated: 1728930591439
created: 1728795953615
---


## What's the best way to specify a "backup URI" for an ontology

- paraphrase: rdfs:isDefinedBy or owl:seeAlso

## could I just specify multiple owl:versionIRIs ?

In RDF/OWL, each ontology version can only have one `owl:versionIRI` property. It uniquely identifies that specific version of the ontology. Specifying multiple `owl:versionIRIs` would break the principle of having a clear and unambiguous version identifier.

However, you can use other properties to specify additional URIs for the ontology, such as:
- **`rdfs:seeAlso`** to link to related URIs or backups.
- **`owl:priorVersion`** for linking to previous versions, effectively creating a chain.
- **Custom properties** like `:backupURI` if you want a dedicated property.

For example:
```turtle
<https://kosmion.github.io/ont/v0/kosmion-v0.ttl> a owl:Ontology ;
    owl:versionIRI <https://kosmion.github.io/ont/v0/kosmion-v0.1.2.ttl> ;
    rdfs:seeAlso <https://kosmion.github.io/ont/backup/kosmion-backup.ttl> .
```

This allows you to point to a backup without conflicting with the versioning structure of OWL. Let me know if this works for you or if you need a different solution!

## I guess owl:versionIRI could be applied to regular "a-box" RDF files too.

(yes) 
- t.2024.10.13.21 but I'd rather not. I don't like versionIRI.

## could an ontology be considered a dataset? if so, how do datasets specify a URL where that dataset is available?

Yes, ontologies can be considered datasets, especially when they include a collection of facts, axioms, or instance data (A-box). The distinction between an "ontology" and a "dataset" can be somewhat blurry—an ontology is a dataset that provides a structured vocabulary and a set of logical relationships to describe a domain, while a dataset often represents actual instance data.

To specify a URL where a dataset (or ontology) is available, you can use the **DCAT (Data Catalog Vocabulary)**, which is commonly used for describing datasets in RDF. You might use properties like `dcat:accessURL` or `dcat:downloadURL` to provide information about where the dataset can be accessed:

1. **Using `dcat:accessURL`**: This property points to a landing page where users can find more information or access the dataset.
2. **Using `dcat:downloadURL`**: This property directly links to the downloadable version of the dataset.

Example in Turtle syntax:

```turtle
@prefix dcat: <http://www.w3.org/ns/dcat#> .

<https://kosmion.github.io/ont/v0/kosmion-v0.1.2.ttl> a dcat:Dataset ;
    dcat:title "Kosmion Ontology Dataset v0.1.2" ;
    dcat:accessURL <https://kosmion.github.io/ont/v0/> ;
    dcat:downloadURL <https://kosmion.github.io/ont/v0/kosmion-v0.1.2.ttl> .
```

This way, you can specify both a landing page (`accessURL`) and a direct link for downloading the dataset (`downloadURL`), providing more flexibility depending on the users' needs.

Let me know if this approach works for your Kosmion ontology or if you'd like to explore other options.


## can rdfs:isDefinedBy have more than one IRI ?

The `rdfs:isDefinedBy` property can technically have multiple IRIs. RDF and RDFS don't enforce any cardinality constraints on `rdfs:isDefinedBy`, so it can point to multiple defining resources. However, this usage might be unusual, and tools or consumers of the ontology might not expect it, as `rdfs:isDefinedBy` is generally intended to specify a single primary source that provides a definition for a resource.

Here's an example of how you could define multiple `rdfs:isDefinedBy` statements:

```turtle
:relator rdfs:isDefinedBy <https://kosmion.github.io/ont/v0/> ;
        rdfs:isDefinedBy <https://another-resource.org/ontology/> .
```

If you use multiple IRIs, be aware that certain tools might only process the first one they encounter or might not support reasoning over multiple definitions seamlessly.

Would you like to add multiple `rdfs:isDefinedBy` IRIs to your ontology, or are you exploring alternatives for defining metadata?


## let's add to ontology-level metadata: dcat:accessURL with https://kosmion.github.io/ontology/v0/ and dcat:downloadURL and owl:versionIRI should both use "https://raw.githubusercontent.com/kosmion/ontology/refs/heads/main/v0/kosmion-v0.1.2.ttl"

I've added the `dcat:accessURL` and updated `dcat:downloadURL` and `owl:versionIRI` as per your instructions. Let me know if there's anything else you'd like to modify or add!

(but incorrectly)

## are instances of owl:Class also subclasses of owl:class ?

In OWL, instances of `owl:Class` are not automatically considered subclasses of `owl:Class`.

- **Instances vs. Subclasses**: An instance of `owl:Class` is treated as an individual, not a subclass. For example, if you declare `:Category a owl:Class ;`, `:Category` is a class. If you declare `:exampleCategory a :Category ;`, `:exampleCategory` is an instance (or individual) of the class `:Category`. It does not mean that `:exampleCategory` is also a subclass of `owl:Class`.

- **Metamodeling and OWL Full**: In OWL Full, classes can simultaneously be individuals and subclasses of other classes because OWL Full does not distinguish between the class and instance level. In OWL DL, which is more restrictive, a class and its instances are kept separate to maintain decidability. If you want the flexibility where instances can also be treated as classes, OWL Full allows that through metamodeling, but it comes at the cost of reasoning support.

If you need instances of `owl:Class` to also act as subclasses in your ontology, you would be working with OWL Full, where it's possible to use the same entity both as a class and an instance. However, most reasoning tools might struggle with such a structure.

## wait, you said it both ways. 

You're right; I may have caused confusion there. Let me clarify:

In OWL, an **instance of `owl:Class`** is not inherently a **subclass of `owl:Class`**. They are two different things:

1. **Instance of `owl:Class`**: When you define an entity as an instance of `owl:Class`, it means that the entity is itself a class that can have instances. For example:
   ```turtle
   :Category a owl:Class .
   ```
   Here, `:Category` is a class, and it can have individuals (instances) associated with it.

2. **Subclass of `owl:Class`**: To declare an entity as a subclass of `owl:Class` would mean you're defining a class that inherits characteristics from `owl:Class`, which generally doesn’t make sense semantically. `owl:Class` is a metaclass, and classes that are instances of `owl:Class` do not become its subclasses automatically.

To use an example from your Kosmion ontology:
- If `:facet-stereotype` is an `owl:Class`, then defining `:category` as an instance means that `:category` is a specific type of `:facet-stereotype`.
- If you need `:category` to also have subclasses, then you'd define it differently, but being an instance of `:facet-stereotype` does not automatically make it a subclass.

In OWL Full, you can do metamodeling, which allows an entity to be both a class and an instance simultaneously, but this is not possible in OWL DL, where the class/instance distinction is stricter.

Let me know if you need more specific examples or adjustments for your ontology!

## After reading [[ar.knowledgegraph.lexrdf-can-owl-class-be-a-subclass-of-one-of-its-own-instances]] -- it seems like I'm just using the RDF semantics, not the direct semantics, so maybe should use rdfs:class instead of owl:class. What do you think, don't change anything yet

It makes sense that using `rdfs:Class` might be more appropriate for your use case, especially if you're primarily using RDF semantics (rather than OWL's more strict semantics). The distinction really depends on how much inference and reasoning power you need from your ontology:

- **`owl:Class`** implies richer semantics and supports reasoning over the ontology using OWL DL or OWL Full, which provides more inferencing capabilities.
- **`rdfs:Class`** is more lightweight and fits better when you need to leverage RDF's flexibility without enforcing OWL constraints.

If your ontology involves a lot of reification-like patterns and mixing instances/classes, using `rdfs:Class` could simplify both modeling and tool compatibility.

Let me know if you decide to switch to `rdfs:Class`, and I can help make those adjustments.

(see also [[vs.rdfs-vs-owl]])

## how do you specify a dataset

To specify a dataset in RDF, you typically use the **DCAT (Data Catalog Vocabulary)** to provide metadata about the dataset. In DCAT, a dataset can be described with properties such as title, description, distribution links, and access URLs. Here is an example:

```turtle
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .

<https://kosmion.github.io/ontology/v0/> a dcat:Dataset ;
    dct:title "Kosmion Ontology Dataset" ;
    dct:description "A foundational ontology designed with a human-first, domain-first approach." ;
    dcat:accessURL <https://kosmion.github.io/ontology/v0/> ;
    dcat:downloadURL <https://raw.githubusercontent.com/kosmion/ontology/refs/heads/main/v0/kosmion-v0.1.2.ttl> ;
    dct:issued "2024-10-11"^^xsd:date ;
    dct:creator <https://kosmion.github.io/creator-profile> .
```

### Key Points:
1. **`dcat:Dataset`**: Declares that the resource is a dataset.
2. **`dct:title` and `dct:description`**: Provide human-readable labels and explanations.
3. **`dcat:accessURL` and `dcat:downloadURL`**: Specify where the dataset can be accessed or downloaded.
4. **`dct:issued`**: Indicates the date the dataset was issued.
5. **`dct:creator`**: Specifies who created the dataset.

This way, you can provide structured metadata for your dataset that tools, consumers, and data catalogs can easily process. Let me know if you want to add this metadata to your current work or if there's anything specific you'd like to discuss further!

## should I use "dct:description" or "rdfs:comment"

The choice between `dct:description` and `rdfs:comment` depends on how you want your metadata to be interpreted and which community standards you're aligning with:

- **`rdfs:comment`**: 
  - Typically used for documentation within the RDF/OWL community.
  - Suitable if you want to provide a textual description about a class or property to help understand its intended use.
  - Works well for ontologies and is easily interpreted by semantic reasoners.

- **`dct:description`**:
  - Part of the Dublin Core Terms vocabulary, commonly used to describe resources in a broader data catalog or metadata context.
  - More common in data cataloging, dataset descriptions, and general metadata that isn't specifically ontology-focused.

If your main focus is to provide rich metadata that could be used in data cataloging or to make your dataset easier to integrate into larger data repositories (like open data portals), then `dct:description` might be more suitable.

However, for ontology-level documentation where you are explaining the purpose and meaning of terms in the ontology, sticking with `rdfs:comment` is more conventional. It is widely supported in RDF/OWL tooling and aligns with existing ontology modeling practices.

In your Kosmion ontology, it seems `rdfs:comment` works well because you are documenting ontology terms for semantic clarity. Let me know if you want to switch or mix these, and we can adjust accordingly.

## I like to think of ontologies as a kind of dataset, one that usually has a preponderance of t-box terms.

Your perspective that ontologies are a kind of dataset, one with a preponderance of T-box (terminology) terms, aligns well with a practical approach to metadata and description. In your case, treating the ontology as a dataset can simplify its representation in data catalogs and make it easier to manage alongside other types of datasets.

This means using vocabularies like **DCAT** to describe the ontology could make a lot of sense, especially if you want it to be discoverable and integratable in a broader ecosystem, similar to how other datasets are cataloged. If you find that `rdfs:Class` fits better because you primarily leverage RDF semantics without needing OWL's reasoning capabilities, switching might also bring more flexibility and tool compatibility.

Let me know if you decide to make any changes, or if you need help switching terms or adjusting metadata to fit your evolving approach.

## the domain of accessURL and downloadURL is a distribution.  what are best practices around what IRI to use for a dataset? Should it return an RDF file? Or just refer to one (or more) RDF files in some returned HTML?

For specifying a dataset with **DCAT**, you typically create two components: the dataset itself and a distribution. Here's how to manage the IRI and what it should return:

### Best Practices for a Dataset IRI
1. **Dataset vs. Distribution**:
   - **Dataset IRI**: This should identify the conceptual dataset. It is a persistent, high-level reference.
   - **Distribution**: Each format of the dataset (e.g., Turtle, JSON-LD) is represented by a `dcat:Distribution`.

2. **Dataset IRI Content**:
   - Ideally, the **dataset IRI** should return **metadata about the dataset**. It could be RDF metadata or an HTML page that provides links to distributions.
   - If it's an HTML page, you could include links that direct users (and machines) to the actual RDF files, usually described as `dcat:distribution`.

3. **Example DCAT Metadata**:
   ```turtle
   @prefix dcat: <http://www.w3.org/ns/dcat#> .
   @prefix dct: <http://purl.org/dc/terms/> .

   <https://kosmion.github.io/ontology/v0/> a dcat:Dataset ;
       dct:title "Kosmion Ontology Dataset" ;
       dct:description "A foundational ontology designed for defining domain-specific constructs." ;
       dcat:distribution <https://kosmion.github.io/ontology/v0/distribution-ttl> .

   <https://kosmion.github.io/ontology/v0/distribution-ttl> a dcat:Distribution ;
       dct:format "text/turtle" ;
       dcat:accessURL <https://raw.githubusercontent.com/kosmion/ontology/refs/heads/main/v0/kosmion-v0.1.2.ttl> .
   ```

4. **Dataset IRI Response**:
   - The **Dataset IRI** (e.g., `<https://kosmion.github.io/ontology/v0/>`) should ideally be a landing page with details about the dataset.
   - This could return an **HTML page** with human-readable descriptions and links, or it could also return **RDF metadata** when accessed via content negotiation (e.g., `Accept: application/rdf+xml`).

5. **Content Negotiation**:
   - You could implement **content negotiation** so that if an agent requests RDF (`Accept: application/ld+json` or `Accept: text/turtle`), it gets metadata in RDF, while regular requests (`Accept: text/html`) return an HTML overview page.

### Recommendations
- Treat the dataset IRI as a point of entry, providing both human-readable and machine-readable content when possible.
- Use **`dcat:Dataset`** to describe the dataset conceptually, and **`dcat:Distribution`** for each physical file that users or agents can access.

Let me know if you want to make adjustments to your existing dataset representation, or if you need help structuring this in the current ontology!

## No content negotation, ever. This is a "static site" solution. I'm going to change things a bit.

Got it, if you're moving away from content negotiation and leaning into a static site model, here are a few suggestions you might consider:

1. **Dataset IRI**: 
   - It might be better to have the dataset IRI point directly to an **HTML page** that provides metadata for humans (e.g., `<https://kosmion.github.io/ontology/v0/>`). This page can also contain links to the distributions in various formats.
  
2. **Distributions**: 
   - You could have separate **distribution IRIs** pointing directly to RDF files in different serializations (e.g., Turtle, JSON-LD). This could look like:
     ```turtle
     dcat:distribution <https://kosmion.github.io/ontology/v0/kosmion-v0.1.2.ttl> , <https://kosmion.github.io/ontology/v0/kosmion-v0.1.2.jsonld> .
     ```

3. **IRI Returns**:
   - If the dataset IRI points to a static HTML page, users will have a clean landing page with the links to available formats, which makes it more user-friendly without requiring dynamic content negotiation.

Feel free to let me know how you want to proceed, and I can help update your current version accordingly!

## is there an rdfs:Ontology ?

No, there is no `rdfs:Ontology` class in the standard RDF Schema vocabulary (`rdfs`). RDF Schema is intended to provide lightweight schema capabilities, primarily dealing with the relationships between classes and properties, but it does not include an explicit notion of an ontology like OWL does.

In RDF Schema, you wouldn't typically have a specific type like `owl:Ontology` that describes an ontology, because RDF Schema is meant to be simpler and lacks formal ontology-level constructs that are part of OWL. If you're shifting away from OWL and want to stay entirely within RDF semantics, you could simply omit the `owl:Ontology` type declaration or use descriptive metadata (like labels, comments, or `dct:subject`).

For example, instead of using `owl:Ontology`:

```turtle
<https://kosmion.github.io/ontology/v0/> a dcat:Dataset ;
    rdfs:label "Kosmion Ontology" ;
    rdfs:comment "A foundational ontology dataset ..." .
```

This way, you treat it as a dataset without needing a formal class like `owl:Ontology`. You could use `rdfs:label` and `rdfs:comment` to provide the necessary descriptive context.

## how do you specify the relationship between a dataset and a distribution

dcat:distribution

- t.2024.10.13.22 I can't believe the class and the property are identical except for the capitalization. 

## how does versioning work with dcat

In **DCAT** (Data Catalog Vocabulary), versioning of datasets is usually handled through properties like `dct:hasVersion`, `dct:isVersionOf`, or by using `owl:versionInfo`. Here are some approaches for managing versioning:

### 1. **Use `dct:hasVersion` and `dct:isVersionOf`**:
   These properties help link different versions of the same dataset. For example:
   ```turtle
   <https://kosmion.github.io/ontology/v0/> a dcat:Dataset ;
       dct:title "Kosmion Ontology Dataset" ;
       dct:description "Version 0.1.2 of the Kosmion ontology." ;
       dct:hasVersion <https://kosmion.github.io/ontology/v0.1.3/> .

   <https://kosmion.github.io/ontology/v0.1.3/> a dcat:Dataset ;
       dct:title "Kosmion Ontology Dataset v0.1.3" ;
       dct:isVersionOf <https://kosmion.github.io/ontology/v0/> ;
       dct:issued "2024-10-12"^^xsd:date .
   ```
   - **`dct:hasVersion`**: Used by the older version to point to the newer one.
   - **`dct:isVersionOf`**: Used by the newer version to reference the original dataset.

### 2. **Use `owl:versionInfo`**:
   This property is already included in your current dataset to provide a version identifier. It's more descriptive rather than linking versions directly:
   ```turtle
   <https://kosmion.github.io/ontology/v0/> a owl:Ontology, dcat:Dataset ;
       owl:versionInfo "v0.1.2" ;
       dcat:distribution <https://kosmion.github.io/ontology/v0/distribution-ttl> .
   ```

### 3. **Create Unique IRIs for Each Version**:
   - Each version of the dataset should have a unique IRI.
   - Use **semantic versioning** in the dataset IRI to distinguish different versions, e.g., `<https://kosmion.github.io/ontology/v0.1.2/>`, `<https://kosmion.github.io/ontology/v0.1.3/>`.

### 4. **Distributions with Version Metadata**:
   Each distribution could also include version metadata to link to a specific dataset version:
   ```turtle
   <https://kosmion.github.io/ontology/v0.1.2/distribution-ttl> a dcat:Distribution ;
       dct:format "text/turtle" ;
       dct:issued "2024-10-12"^^xsd:date ;
       dcat:accessURL <https://raw.githubusercontent.com/kosmion/ontology/refs/heads/main/v0.1.2/kosmion-v0.1.2.ttl> ;
       dct:isPartOf <https://kosmion.github.io/ontology/v0.1.2/> .
   ```

### Recommendations:
- **Link Versions**: Use `dct:hasVersion` and `dct:isVersionOf` to create a chain of versions.
- **Distinct IRIs**: Ensure each version has a distinct IRI so that users can reference a specific version unambiguously.
- **Use `dcat:Dataset` and `dcat:Distribution`**: Continue using the dataset-distribution relationship to differentiate between the conceptual dataset and its individual downloadable files.

If you'd like, I can help you adjust your existing Turtle content to include these versioning relationships. Just let me know!

(also see https://github.com/w3c/dxwg/issues/1280 which recommends owl:versionInfo, and a comment "We hedged our bets and provided multiple alternative options everywhere, allowing for almost every variation that anyone asked for. Big mistake." )


## If I wanted to use prov:wasRevisionOf would I have to say `<https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/ttl> a prov:Entity` ?

Yes, if you want to use **`prov:wasRevisionOf`** to indicate that a distribution is a revision of a previous version, then you would need to declare the entity explicitly as a **`prov:Entity`**. In the PROV ontology, `prov:Entity` represents a resource that can have provenance information (such as being a revision of another entity).

Here's how you could specify it:

```turtle
<https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/ttl> a dcat:Distribution, prov:Entity ;
    prov:wasRevisionOf <https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.1/ttl> .
```

In this statement:
- **`a prov:Entity`**: Declares that the IRI is an entity that can have provenance relationships.
- **`prov:wasRevisionOf`**: Indicates the relationship between this distribution and the previous version.

Using both `dcat:Distribution` and `prov:Entity` allows you to handle both the data catalog aspect (distribution) and the provenance information (revision relationship). Let me know if you need to add this or make any other changes!

## Can dcat:Distribution refer to different versions as well as formats?

...

Regarding whether **`dcat:Distribution`** can be used to refer to both **formats** and **versions**, it’s technically feasible, but it can introduce complexity. Here's a breakdown:

### Using `dcat:Distribution` for Different Versions
You can use `dcat:Distribution` to represent different versions of the dataset by distinguishing each version through the IRI and including additional metadata to identify the specific version. For example:

```turtle
<https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/ttl> a dcat:Distribution, prov:Entity ;
    dct:format "text/turtle" ;
    prov:wasRevisionOf <https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.1/ttl> ;
    dcat:accessURL <https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/ttl> .
```

### Pros and Cons
- **Pros**:
  - By treating each distribution as a `prov:Entity` and using `prov:wasRevisionOf`, you clearly establish version history at the level of the distribution. This is useful when tracking specific file versions, especially if multiple serializations exist for each version.
  - It's a clean approach to show lineage if each distribution version is seen as an independent, versioned entity.

- **Cons**:
  - It can become harder to distinguish between changes in **formats** and changes in **versions**. For example, a Turtle serialization of version `0.1.2` could be revised without changing the version of the ontology, which might lead to ambiguity if both are treated as `dcat:Distribution`.
  - To keep this organized, you'd need to add properties like `dct:version` or manage metadata for distinguishing between format-level changes and ontology version changes.

### Recommendation
- **Separate Distributions by Version and Format**:
  - Consider organizing the **distributions** IRIs by **version** and **format** to reduce ambiguity. Each `dcat:Distribution` should clearly represent a specific version and format.
  - Example:
    ```turtle
    <https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/ttl> a dcat:Distribution, prov:Entity ;
        dct:format "text/turtle" ;
        prov:wasRevisionOf <https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.1/ttl> ;
        dcat:accessURL <https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/ttl> .

    <https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/jsonld> a dcat:Distribution ;
        dct:format "application/ld+json" ;
        dcat:accessURL <https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/jsonld> .
    ```

- **Dataset IRI for Versioning**:
  - Use the **dataset** IRI (e.g., `<https://kosmion.github.io/datasets/ontology/v0/>`) to describe the ontology conceptually and indicate breaking changes by updating `/v0` to `/v1`.
  - Use `prov:wasRevisionOf` and similar properties at the **distribution level** to track revisions of specific ontology versions.

Let me know if this approach makes sense for your use case or if you'd like to explore a different organization for versions and formats.


## for the distribution IRI, https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/ttl/ is adequate, right? no need to return RDF there.

Yes, using the distribution IRI as **`https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/ttl/`** is adequate and appropriate. Since this IRI represents a **directory-like structure** pointing to a particular version and format, there’s no requirement for it to return RDF content directly. Instead, it serves as a logical grouping or access point for the different resources of that version.

The key thing is that:
- The **`owl:versionIRI`** should still point directly to the specific RDF file for that version (`https://kosmion.github.io/datasets/ontology/v0/distributions/v0.1.2/ttl/kosmion-v0.1.2.ttl`).
- The **distribution IRI** can serve as a landing page or directory containing multiple related resources.

In your current setup, this is correctly managed: the `distribution IRI` provides an access point for browsing, while `downloadURL` points to the actual RDF file, and `owl:versionIRI` meets the OWL requirement of providing RDF content. This approach should work well in terms of both organization and accessibility.


## dct:title vs rdfs:label

The choice between `dct:title` and `rdfs:label` largely depends on the context of usage and the semantics you want to convey:

- **`dct:title`** is more descriptive and is typically used for datasets, documents, or resources that have a formal title. It's part of the Dublin Core Metadata Terms vocabulary, which is well-suited for describing resources in a cataloging context, making it ideal for datasets or documents.

- **`rdfs:label`** is generally used to provide a human-readable name for a resource, class, or property in RDF. It's often shorter, more generic, and typically meant for use in ontology documentation or UI interfaces.

### Recommendations for Your Case
- **Ontology/Dataset Level**: 
  Since `<https://kosmion.github.io/datasets/ontology/v0/>` is both a dataset and an ontology, it might make sense to use both properties:
  - Use **`dct:title`** to specify the formal title of the dataset, making it more compatible with cataloging tools.
  - Use **`rdfs:label`** to provide a simpler, human-readable name that is typically used in ontologies.

  Example:
  ```turtle
  <https://kosmion.github.io/datasets/ontology/v0/> a owl:Ontology, dcat:Dataset ;
      dct:title "Kosmion Ontology Dataset v0" ;
      rdfs:label "Kosmion ontology" ;
      rdfs:comment """...""" .
  ```

This way, you're making your dataset well-described for data cataloging purposes while still providing an easily recognizable label for ontology-specific tools.

Would you like me to make these changes for you?

## Is it more conventional/sensible to provide dct:issued/modified with the Distriution or with the Dataset? 

It is more conventional to apply **`dct:issued`** and **`dct:modified`** at both the **Dataset** and **Distribution** levels, but they serve slightly different purposes:

### 1. **Dataset Level (`dcat:Dataset`)**:
   - **`dct:issued`**: Indicates the creation or publication date of the entire dataset. It represents when the dataset as a conceptual whole was first made available.
   - **`dct:modified`**: Indicates the last time the dataset (as a conceptual entity) was updated, which might include adding new distributions, making modifications to descriptions, etc.

   Applying `dct:issued` and `dct:modified` here allows users to understand the overall lifecycle of the dataset.

### 2. **Distribution Level (`dcat:Distribution`)**:
   - **`dct:issued`**: Refers to the creation date of that specific distribution. This can be different from the dataset-level `dct:issued` if the distribution was added after the original dataset release.
   - **`dct:modified`**: Refers to the last time the specific distribution was modified. For example, when a Turtle file is updated to reflect changes in the dataset.

   Applying `dct:issued` and `dct:modified` at the distribution level helps users track the specific versions and changes to the individual data files.

### Summary:
- **Dataset (`dcat:Dataset`)**: Use `dct:issued` and `dct:modified` to indicate the lifecycle of the overall dataset.
- **Distribution (`dcat:Distribution`)**: Use `dct:issued` and `dct:modified` for versioning and modification information specific to each individual distribution (e.g., Turtle, JSON-LD files).

This dual-level application provides a clear view of when the dataset as a whole was created or updated, as well as when individual data files were published or revised.

Would you like me to add `dct:issued` and `dct:modified` to both the dataset and distribution definitions in your ontology?


## 