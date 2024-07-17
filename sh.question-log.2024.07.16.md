---
id: 8sgd68mwmplexhdc0xnniza
title: '16'
desc: ''
updated: 1721200450925
created: 1721189887288
---

## thinking about the directory structure of my ontology again, and how different major versions are actually different ontologies. also, I like ns for the next level under the ontology url. so /kosmion/v1/ns/ as the ontology version IRI, and /kosmion/ns/ as the ontology IRI. may as well do the same thing with the docs, since they might be version-specific. So /kosmion/ns/docs for current docs, and /kosmion/ns/v1/docs for version docs. 

That sounds like a clear and organized structure, allowing for both current and version-specific ontologies and documentation. Using "ns" for the namespace level and organizing by versions makes it easy to manage and navigate different versions of your ontology and their respective documentation.

Here’s a detailed directory structure based on your preferences:

### Directory Structure

```
kosmion.github.io/
├── index.html                # Homepage with an overview
├── ns/                       # Namespace for current ontology version
│   ├── index.html            # Overview of the current ontology
│   ├── kosmion.owl           # Current main ontology file (OWL format)
│   ├── kosmion.ttl           # Current main ontology file (Turtle format)
│   ├── creature/             # Directory for the Creature class
│   │   └── index.html        # Documentation for the Creature class
│   ├── person/               # Directory for the Person class
│   │   └── index.html        # Documentation for the Person class
│   ├── animal/               # Directory for the Animal class
│   │   └── index.html        # Documentation for the Animal class
│   ├── hasName/              # Directory for the hasName property
│   │   └── index.html        # Documentation for the hasName property
│   ├── hasAge/               # Directory for the hasAge property
│   │   └── index.html        # Documentation for the hasAge property
│   └── hasPower/             # Directory for the hasPower property
│       └── index.html        # Documentation for the hasPower property
├── docs/                     # Current documentation directory
│   ├── index.html            # Documentation homepage
│   ├── guide.html            # User guides
│   └── api.html              # API documentation
├── v1/                       # Directory for version 1 of the ontology and docs
│   ├── ns/                   # Namespace for version 1 ontology
│   │   ├── index.html        # Overview of version 1 ontology
│   │   ├── kosmion.owl       # Version 1 ontology file (OWL format)
│   │   ├── kosmion.ttl       # Version 1 ontology file (Turtle format)
│   │   ├── creature/         # Directory for the Creature class in v1
│   │   │   └── index.html    # Documentation for the Creature class in v1
│   │   ├── person/           # Directory for the Person class in v1
│   │   │   └── index.html    # Documentation for the Person class in v1
│   │   ├── animal/           # Directory for the Animal class in v1
│   │   │   └── index.html    # Documentation for the Animal class in v1
│   │   ├── hasName/          # Directory for the hasName property in v1
│   │   │   └── index.html    # Documentation for the hasName property in v1
│   │   ├── hasAge/           # Directory for the hasAge property in v1
│   │   │   └── index.html    # Documentation for the hasAge property in v1
│   │   └── hasPower/         # Directory for the hasPower property in v1
│   │       └── index.html    # Documentation for the hasPower property in v1
│   └── docs/                 # Documentation for version 1
│       ├── index.html        # Documentation homepage for v1
│       ├── guide.html        # User guides for v1
│       └── api.html          # API documentation for v1
└── other_files/              # Any other files or folders
```

### Example Content

#### ns/index.html (Current Ontology)

```html
<!DOCTYPE html>
<html>
<head>
    <title>Kosmion Ontology Namespace</title>
</head>
<body>
    <h1>Welcome to the Kosmion Ontology Namespace</h1>
    <p>This directory contains the current version of the Kosmion ontology elements, including classes, properties, and the ontology file itself.</p>
    <ul>
        <li><a href="kosmion.owl">Download Ontology (OWL)</a></li>
        <li><a href="kosmion.ttl">Download Ontology (Turtle)</a></li>
        <li><a href="creature/">Creature Class</a></li>
        <li><a href="person/">Person Class</a></li>
        <li><a href="animal/">Animal Class</a></li>
        <li><a href="hasName/">hasName Property</a></li>
        <li><a href="hasAge/">hasAge Property</a></li>
        <li><a href="hasPower/">hasPower Property</a></li>
    </ul>
</body>
</html>
```

#### v1/ns/index.html (Version 1 Ontology)

```html
<!DOCTYPE html>
<html>
<head>
    <title>Kosmion Ontology Namespace - Version 1</title>
</head>
<body>
    <h1>Welcome to the Kosmion Ontology Namespace - Version 1</h1>
    <p>This directory contains the elements of version 1 of the Kosmion ontology, including classes, properties, and the ontology file itself.</p>
    <ul>
        <li><a href="kosmion.owl">Download Ontology (OWL)</a></li>
        <li><a href="kosmion.ttl">Download Ontology (Turtle)</a></li>
        <li><a href="creature/">Creature Class</a></li>
        <li><a href="person/">Person Class</a></li>
        <li><a href="animal/">Animal Class</a></li>
        <li><a href="hasName/">hasName Property</a></li>
        <li><a href="hasAge/">hasAge Property</a></li>
        <li><a href="hasPower/">hasPower Property</a></li>
    </ul>
</body>
</html>
```

### URL Structure

- **Current Ontology**:
- `https://kosmion.github.io/ns/
(elided)


### Summary

This structure ensures that both current and version-specific ontologies and documentation are well-organized and easily navigable. By using "ns" for the namespace and organizing by versions, you can manage different versions of your ontology and their respective documentation effectively.

- **Top Level**: General resources.
- **ns**: Contains the current ontology elements and documentation.
- **v1/ns**: Contains version 1 ontology elements.
- **v1/docs**: Contains version 1 documentation.

This approach provides a clear, consistent, and scalable structure that supports both current and historical versions of your ontology and documentation.


## (a lot of refinement later)

Sure, let's update the structure to accommodate multiple ontologies under the `ont/` directory. Each ontology will have its own subdirectory, such as `ont/kosmion`. This allows for modular support and offline use cases.

### Updated Directory Structure

```
Certainly! Here is the directory hierarchy using indented list item format:

```
kosmion.github.io/
    index.html                # Homepage with an overview and links
    ns/                       # Namespace for all named IRIs
        index.html            # Introductory page for namespace
        creature/             # Directory for the Creature class
            index.html        # Redirect or disambiguation for the Creature class
        person/               # Directory for the Person class
            index.html        # Redirect or disambiguation for the Person class
        animal/               # Directory for the Animal class
            index.html        # Redirect or disambiguation for the Animal class
        hasName/              # Directory for the hasName property
            index.html        # Redirect or disambiguation for the hasName property
        hasAge/               # Directory for the hasAge property
            index.html        # Redirect or disambiguation for the hasAge property
        hasPower/             # Directory for the hasPower property
            index.html        # Redirect or disambiguation for the hasPower property
    ont/                      # Ontology files directory
        index.html            # Introductory page for ontologies
        kosmion/              # Kosmion ontology directory
            index.html        # Client-side redirect to the current version ontology files
            v1/               # Directory for version 1 of the Kosmion ontology
                index.html    # RDFa version of the version 1 ontology
                kosmion_ontology.ttl     # Version 1 ontology file (Turtle format)
                kosmion_ontology.jsonld  # Version 1 ontology file (JSON-LD format)
                ns/           # Namespace for version 1 ontology
                    index.html # RDFa version of the version 1 ontology
                    creature/  # Directory for the Creature class in v1
                        index.html # Documentation for the Creature class in v1
                    person/    # Directory for the Person class in v1
                        index.html # Documentation for the Person class in v1
                    animal/    # Directory for the Animal class in v1
                        index.html # Documentation for the Animal class in v1
                    hasName/   # Directory for the hasName property in v1
                        index.html # Documentation for the hasName property in v1
                    hasAge/    # Directory for the hasAge property in v1
                        index.html # Documentation for the hasAge property in v1
                    hasPower/  # Directory for the hasPower property in v1
                        index.html # Documentation for the hasPower property in v1
                docs/          # Documentation for version 1
                    index.html # Documentation homepage for v1
                    guide.html # User guides for v1
                    api.html   # API documentation for v1
                examples/      # Examples directory for version 1
                    index.html # Examples homepage for version 1
                    example1.html # Example 1 for version 1
    docs/                     # Documentation directory
        index.html            # Introductory page for documentation
    data/                     # Data directory for non-ontological data
        index.html            # Overview of data files
        gunaar.ttl            # Example Turtle data file
        recipe.json-ld        # Example JSON-LD data file
        loot.csv              # Example CSV data file
        places.md             # Example Markdown data file
    terms/                    # Natural language terms indexing
        index.html            # Overview of terms
        en/                   # English terms
            index.html        # Overview of English terms
            example.html      # Example English term file
        jp/                   # Japanese terms
            index.html        # Overview of Japanese terms
            example.html      # Example Japanese term file
``````

### Top-Level index.html

```html
<!DOCTYPE html>
<html>
<head>
    <title>Kosmion Ontology</title>
</head>
<body>
    <h1>Welcome to the Kosmion Ontology</h1>
    <p>This site hosts the Kosmion ontology and its documentation. Use the links below to navigate the resources.</p>
    <ul>
        <li><a href="ns/">Namespace</a></li>
        <li><a href="ont/">Ontology Files</a></li>
        <li><a href="docs/">Documentation</a></li>
        <li><a href="data/">Data</a></li>
        <li><a href="terms/">Terms</a></li>
    </ul>
</body>
</html>
```

### Namespace index.html

#### ns/index.html

```html
<!DOCTYPE html>
<html>
<head>
    <title>Kosmion Ontology Namespace</title>
</head>
<body>
    <h1>Kosmion Ontology Namespace</h1>
    <p>This directory contains the named elements of the Kosmion ontology. Use the links below to navigate the resources.</p>
    <ul>
        <li><a href="../ont/kosmion/v1/ns/creature/">Creature Class</a></li>
        <li><a href="../ont/kosmion/v1/ns/person/">Person Class</a></li>
        <li><a href="../ont/kosmion/v1/ns/animal/">Animal Class</a></li>
        <li><a href="../ont/kosmion/v1/ns/hasName/">hasName Property</a></li>
        <li><a href="../ont/kosmion/v1/ns/hasAge/">hasAge Property</a></li>
        <li><a href="../ont/kosmion/v1/ns/hasPower/">hasPower Property</a></li>
    </ul>
</body>
</html>
```

### Ontology Files index.html with Redirect

#### ont/index.html

```html
<!DOCTYPE html>
<html>
<head>
    <title>Ontologies</title>
</head>
<body>
    <h1>Available Ontologies</h1>
    <p>Select an ontology to explore its versions and resources:</p>
    <ul>
        <li><a href="kosmion/">Kosmion Ontology</a></li>
        <!-- Add other ontologies as needed -->
    </ul>
</body>
</html>
```

#### ont/kosmion/index.html

```html
<!DOCTYPE html>
<html>
<head>
    <title>Redirecting to Current Ontology Files</title>
    <meta http-equiv="refresh" content="0; URL=https://kosmion.github.io/ont/kosmion/v1/">
    <script type="text/javascript">
        window.location.href = "https://kosmion.github.io/ont/kosmion/v1/"
    </script>
</head>
<body>
    <p>If you are not redirected automatically, follow this <a href="https://kosmion.github.io/ont/kosmion/v1/">link to the current version of the Kosmion ontology</a>.</p>
</body>
</html>
```

### Versioned Namespace index.html with RDFa and JSON-LD

#### ont/kosmion/v1/ns/index.html

```html
<!DOCTYPE html>
<html prefix="owl: http://www.w3.org/2002/07/owl# rdfs: http://www.w3.org/2000/01/rdf-schema# xsd: http://www.w3.org/2001/XMLSchema#">
<head>
    <title>Kosmion Ontology Namespace - Version 1</title>
    <script type="application/ld+json">
    {
        "@context": {
            "@vocab": "http://www.w3.org/2002/07/owl#",
            "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
            "xsd": "http://www.w3.org/2001/XMLSchema#"
        },
        "@type": "Ontology",
        "versionIRI": "http://kosmion.github

.io/ont/kosmion/v1/ns/",
        "comment": "This is the JSON-LD representation of version 1 of the Kosmion ontology.",
        "contains": [
            {
                "@type": "Class",
                "@id": "http://kosmion.github.io/ont/kosmion/v1/ns/creature",
                "rdfs:label": "Creature",
                "rdfs:comment": "A class representing mythical creatures in the Kosmion ontology."
            },
            {
                "@type": "Class",
                "@id": "http://kosmion.github.io/ont/kosmion/v1/ns/person",
                "rdfs:label": "Person",
                "rdfs:comment": "A class representing individuals in the Kosmion ontology."
            },
            {
                "@type": "Class",
                "@id": "http://kosmion.github.io/ont/kosmion/v1/ns/animal",
                "rdfs:label": "Animal",
                "rdfs:comment": "A class representing animals in the Kosmion ontology."
            }
            // Add more class definitions as needed
        ]
    }
    </script>
</head>
<body>
    <h1>Welcome to the Kosmion Ontology Namespace - Version 1</h1>
    <p>This directory contains version 1 of the Kosmion ontology elements, including classes, properties, and the ontology file itself.</p>
    <ul>
        <li><a href="../kosmion_ontology.ttl">Download Ontology (Turtle)</a></li>
        <li><a href="../kosmion_ontology.jsonld">Download Ontology (JSON-LD)</a></li>
        <li><a href="creature/">Creature Class</a></li>
        <li><a href="person/">Person Class</a></li>
        <li><a href="animal/">Animal Class</a></li>
        <li><a href="hasName/">hasName Property</a></li>
        <li><a href="hasAge/">hasAge Property</a></li>
        <li><a href="hasPower/">hasPower Property</a></li>
    </ul>
    
    <div vocab="http://www.w3.org/2002/07/owl#" typeof="Ontology">
        <h2>Ontology Details</h2>
        <div property="versionIRI" resource="http://kosmion.github.io/ont/kosmion/v1/ns/"/>
        <div property="comment" content="This is the RDFa representation of version 1 of the Kosmion ontology.">
        </div>
        <div typeof="Class" resource="http://kosmion.github.io/ont/kosmion/v1/ns/creature">
            <div property="rdfs:label">Creature</div>
            <div property="rdfs:comment">A class representing mythical creatures in the Kosmion ontology.</div>
        </div>
        <div typeof="Class" resource="http://kosmion.github.io/ont/kosmion/v1/ns/person">
            <div property="rdfs:label">Person</div>
            <div property="rdfs:comment">A class representing individuals in the Kosmion ontology.</div>
        </div>
        <div typeof="Class" resource="http://kosmion.github.io/ont/kosmion/v1/ns/animal">
            <div property="rdfs:label">Animal</div>
            <div property="rdfs:comment">A class representing animals in the Kosmion ontology.</div>
        </div>
        <!-- Add more RDFa definitions as needed -->
    </div>
</body>
</html>
```

### Data index.html

#### data/index.html

```html
<!DOCTYPE html>
<html>
<head>
    <title>Data Files</title>
</head>
<body>
    <h1>Data Files</h1>
    <p>This directory contains various data files used in the Kosmion project. Use the links below to explore the data files.</p>
    <ul>
        <li><a href="gunaar.ttl">Gunaar (Turtle)</a></li>
        <li><a href="recipe.json-ld">Recipe (JSON-LD)</a></li>
        <li><a href="loot.csv">Loot (CSV)</a></li>
        <li><a href="places.md">Places (Markdown)</a></li>
    </ul>
</body>
</html>
```

This structure provides clear organization for the ontology elements, ontology versions, and other data files, while also allowing for modular support for additional ontologies.

