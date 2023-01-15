---
id: bYuGhUNMCc1tbSkWFyJzG
title: Graph Query Language
desc: GQL is a query lanaguage for property graphs
updated: 1638374743958
created: 1638374497732
---



- [[p.hasRelatedResource]] https://en.wikipedia.org/wiki/Graph_Query_Language#The_GQL_property_graph_data_model {2021-12-01 01:29}
  - [[p.hasHighlight]]
    - GQL is a query language specifically for property graphs. A property graph closely resembles a conceptual data model, as expressed in an entity–relationship model or in a UML class diagram (although it does not include n-ary relationships linking more than two entities). Entities or concepts are modelled as nodes, and relationships as edges, in a graph. Property graphs are multigraphs: there can be many edges between the same pair of nodes. GQL graphs can be mixed: they can contain directed edges, where one of the endpoint nodes of an edge is the tail (or source) and the other node is the head (or target or destination), but they can also contain undirected (bidirectional or reflexive) edges.
    - [[p.vs]] [[prdct.tinkerpop]] [[prdct.neo4j]]
      - Current graph database products and projects often support a limited version of the model described here. For example, Apache Tinkerpop forces each node and each edge to have a single label; Cypher allows nodes to have zero to many labels, but relationships only have a single label (called a reltype). Neo4j's database supports undocumented graph-wide properties, Tinkerpop has graph values which play the same role, and also supports "metaproperties" or properties on properties. 
