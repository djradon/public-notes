---
id: 22193vpn9mrpiunwmsh5al5
title: VocBench
desc: 'web-based, multilingual, collaborative development platform for managing OWL ontologies, SKOS(/XL) thesauri, Ontolex-lemon lexicons and generic RDF datasets'
updated: 1729104546254
created: 1717001730540
---

- https://vocbench.uniroma2.it/
- built-on: [[prdct.semantic-turkey]]
- repo: https://bitbucket.org/art-uniroma2/vocbench3/src/master/

![[prdct.protege#similar]]

## Issues

![[pub.question-log.2024.10.16#limitations-of-vocbench]]

## Docs

### Namespaces and Imports section

The imports panel in the Namespace and Imports section allows the authorized user to owl:import ontology vocabularies into the current project. The menu offers five options:

-   Web: imports the ontology by looking on the web for it, using the URI of the ontology for localization
-   Local file: imports the ontology from a local file available in the hard disk
-   Ontology mirror: imports the ontology directly from the ontology mirror
-   Dataset catalog: imports the ontology exploiting the [Dataset Catalog](https://vocbench.uniroma2.it/doc/user/namespaces_imports.jsfdataset_catalogs.jsf)
-   Local project: imports the ontology from a local project

### Dataset Catalogs

-   [Linked Open Vocabularies](https://lov.linkeddata.es/) (LOV): this is a catalog of vocabularies (OWL ontologies and RDFS schemas), which is curated by human editors to assure the quality of its content and accompanying metadata. Individual entries in LOV are associated with an URL to download a cached copy of the vocabulary, but no SPARQL endpoint is provided (since vocabularies are generally intended for the description of the content of other datasets and are thus made available as files).
-   [The Linked Open Data Cloud](https://lod-cloud.net/): this is the home of the repository behind the famous diagram depicting the datasets being published and interconnected using the [Linked Data](https://www.w3.org/DesignIssues/LinkedData.html) best practices and made available as [open data](https://opendefinition.org/). Actually, the documentation of the catalog does not prescribe anything on the license, beyond stating that "Access of the entire dataset must be possible via RDF crawling, via an RDF dump, or via a SPARQL endpoint." (more about technical openness than legal concerns about reusability).
-   [data.europa.eu](https://data.europa.eu): The official portal for European data, providing access to a collection of open dataset metadata harvested from international, EU, national, regional, local and geo data portals. It replaces the EU Open Data Portal and the European Data Portal.
-   [ShowVoc](http://showvoc.uniroma2.it/): an open-source software for creating data portals. Initially developed in the context of the [ISA<sup>2</sup>](https://ec.europa.eu/isa2/) action [Public Multilingual Knowledge Management Infrastructure for the Digital Single Market (PMKI)](https://ec.europa.eu/isa2/actions/overcoming-language-barriers), ShowVoc can be used to set up data portals for specific institutions, companies, etc. ShowVoc is based on the RDF service platform [Semantic Turkey](http://semanticturkey.uniroma2.it/), which also supports VocBench. ShowVoc stores a copy of [stable contributions](http://showvoc.uniroma2.it/doc/user/contributions_submission.jsf#stable_resource_contribution) in projects alike the ones used in VocBench. Moreover, ShowVoc adopts a dedicated policy to grant anyone access to _public datasets_, whereas in VocBench users must be [assigned to projects](https://vocbench.uniroma2.it/doc/user/dataset_catalogs.jsfprojects_adm.jsf#project-users_management). Furthermore, faceted search is based on [project facets](https://vocbench.uniroma2.it/doc/user/dataset_catalogs.jsfuser/projects.jsf#project_facets), both standard ones (e.g. _model_ and _lexicalization model_) and custom ones (decided for each ShowVoc installation).
-   [[prdct.ontoportal]]: an open-source software for creating data portals based on the code originally written for the [BioPortal](https://bioportal.bioontology.org/) ontology repository. In addition to the latter, which has become a reference with respect to biomedical ontologies, other installations cover different domains, such agriculture and environment, which are addressed by [AgroPortal](http://agroportal.lirmm.fr/) and [EcoPortal](https://ecoportal.lifewatch.eu/), respectively. VocBench provides a general configuration targeting any OntoPortal installation, together with one specific for EcoPortal.