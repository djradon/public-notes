---
id: ipi4rlc29200er1dhrxvog3
title: Provencance, Authoring, Versioning Ontology (PAV)
desc: ''
updated: 1730140764063
created: 1729977019216
---

- https://pav-ontology.github.io/pav/
- docs: https://github.com/pav-ontology/pav/wiki/

![](/assets/images/2024-10-26-14-13-31.png)

## Highlights

### createdBy vs authoredBy vs curatedBy vs createdWith vs contributedBy

- createdBy indicates the agent primary responsible for making the digital artifact or resource representation.
- authoredBy indicates who authored the knowledge expressed by this resource
- curatedBy indicates who curated the knowledge into its current form.

#### Examples

- the author wrote 'this species has bigger wings than normal' in his log book. The curator, going through the log book and identifying important knowledge, formalizes this as 'locus perculus has wingspan > 0.5m'. The creator enters this knowledge as a digital resource in the knowledge system, thus creating the digital artifact (say as JSON, RDF, XML or HTML).
- a news article. pav:authoredBy indicates the journalist who wrote the article. pav:contributedBy can indicate the artist who added an illustration. pav:curatedBy can indicate the editor who made the article conform to the news paper's style. pav:createdBy can indicate who put the article on the web site.

### importedFrom

The original source of imported information.

Import means that the content has been preserved, but transcribed somehow, for instance to fit a different representation model by converting formats. Examples of import are when the original was JSON and the current resource is RDF, or where the original was an document scan, and this resource is the plain text found through OCR.

The imported resource does not have to be complete, but should be consistent with the knowledge conveyed by the original resource.

If additional knowledge has been contributed, pav:derivedFrom would be more appropriate.

If the resource has been copied verbatim from the original representation (e.g. downloaded), use pav:retrievedFrom.


### hasCurrentVersion

-  