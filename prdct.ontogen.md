---
id: lo2gql2l1s4q9n27m52bao8
title: Ontogen
desc: 'a vocabulary for RDF compounds, with versioning'
updated: 1723919424835
created: 1723554173768
---

- https://ontogen.io/
- tested-with: [[prdct.jena.fuseki]] and [[prdct.oxigraph]]
- related: [[prdct.rtc-ex]]
- docs: https://ontogen.io/docs/user-guide/

## Features

- RDF Triple Compounds (RTC) allow named-graph-like functionality without using named graphs
- uses [[prdct.RDF-star]] for annotations

### Versioning

- the version-controlled data in Ontogen is kept in a triple store.
- A SpeechAct represents a group of changes to the repository, similar to a commit in traditional VCS, but with additional metadata such as speaker, timestamp, and data source.
- SpeechActs are prepared through the staging system and then stored as commits in the repository.
- This staging system allows users to carefully prepare and review changes before they are committed as a SpeechAct. It provides more control and transparency in the versioning process, especially when working with complex RDF data.

#### Staging file

- Instead of an implicitly held staging area, there is a single staging file with which the next SpeechAct to be committed can be incrementally prepared. 
- By default, this file is called STAGE.trig and contains an RDF dataset consisting of specially named graphs for the different action types:
  -   `og:Addition` graph with changes that should simply be added to the repository without overwriting existing statements
  -   `og:Update` graph with changes that should overwrite existing statements with the same subject and predicate
  -   `og:Replacement` graph with changes that should replace all existing statements with the same subject
  -   `og:Removal` graph with statements that should be removed from the repository
-   currently only one SpeechAct per staging file
-   in addition to TriG, N-Quads (with file extension .nq) and JSON-LD (with file extension .jsonld) are also supported.


## References

- [[ar.ontogen.introducing-ontogen]] 