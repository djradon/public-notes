---
id: ZHoWejqsahUxF64lbKCL1
title: Knowledge Graph Toolkit
desc: 'KTGK is a Python library for easy manipulation with knowledge graphs'
updated: 1638293144347
created: 1638291910197
---

- [[p.hasRepository]] https://github.com/usc-isi-i2/kgtk/
- [[p.hasFeature]]
  - A notable feature of KGTK is that edges are also nodes
    - [[p.hasSource]] https://kgtk.readthedocs.io/en/latest/data_model/
  - KGTK represents KGs using TSV files with 4 columns labeled id, node1, label and node2
    - id column is a symbol representing an identifier of an edge
  - Given that edges are nodes, it is possible to define edges that connect edges to other nodes, as illustrated using the blue arrows.
- [[p.canImportFrom]]
  - [[soln.tsv]]

- [[p.vs]] 
  - [[t.cs.graph.property-graph]]
    - The KGTK model is a generalization of property graphs because the attribute/value pairs are also edges: the attributes are relations and the values can be arbitrary nodes.
  - [[t.cs.graph.semantic-graph]]
    - To represent edges about edges, RDF uses reification, typically done using rdf:Statement, where the edges are represente using three triples. The KGTK representation is simpler as it does not require the creation of extra triples to represent the edges.


