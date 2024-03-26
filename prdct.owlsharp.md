---
id: 3jdualhm8au5civ6lurhblx
title: OWLSharp
desc: 'Lightweight and friendly .NET library for realizing intelligent Semantic Web applications '
updated: 1709078770593
created: 1709078671765
---

- repo: https://github.com/mdesalvo/OWLSharp

![](/assets/images/2024-02-27-16-06-04.png)

## Features

- OWLSharp is built atop [RDFSharp](https://github.com/mdesalvo/RDFSharp) with the goal of providing ontology expressivity for:

-   Creating **OWL2 ontologies** (classes, restrictions, properties, individuals, assertions, annotations, ...)
-   Exporting them using standard **OWL2 formats** (OWL2/Xml)
-   Validating and Reasoning through extensible sets of intelligent **RDFS/OWL-DL/OWL2** semantic rules

In addition to the [core ontology features](https://github.com/mdesalvo/OWLSharp/releases/download/v3.10.2/OWLSharp-3.10.2.pdf), it integrates a set of extensions providing expressivity for:

-   Creating reasoners building business-logic inference rules in a fluent and natural way ([SWRL](https://github.com/mdesalvo/OWLSharp/releases/download/v3.10.0/OWLSharp.Extensions.SWRL-3.10.0.pdf)) 
    -   "infers complex relations between classes
and between properties (driven by feature-
parity with Pellet, HermiT and Fact++"
-   Creating schemes describing, documenting and organizing vocabularies of concepts ([SKOS](https://github.com/mdesalvo/OWLSharp/releases/download/v3.10.0/OWLSharp.Extensions.SKOS-3.10.0.pdf))
-   Modeling and relating features having a spatiotemporal representation ([GeoSPARQL](https://github.com/mdesalvo/OWLSharp/releases/download/v3.10.0/OWLSharp.Extensions.GEO-3.10.0.pdf), [OWL-TIME](https://github.com/mdesalvo/OWLSharp/releases/download/v3.10.0/OWLSharp.Extensions.TIME-3.10.0.pdf))