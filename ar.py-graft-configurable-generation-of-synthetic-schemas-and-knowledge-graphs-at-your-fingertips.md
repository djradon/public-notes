---
id: b5hu8kfmzaudd5wenbx369u
title: >-
  Py Graft Configurable Generation of Synthetic Schemas and Knowledge Graphs at
  Your Fingertips
desc: ''
updated: 1713198535819
created: 1713197740775
---


- https://arxiv.org/pdf/2309.03685.pdf
- topics: [[t.km.knowledge-graph]] [[t.cs.semantic-web]] [[prdct.pygraft]]

## Abstract

- Knowledge graphs (KGs) have emerged as a prominent data
representation and management paradigm. Being usually underpinned
by a schema (e.g., an ontology), KGs capture not only factual informa-
tion but also contextual knowledge. In some tasks, a few KGs established
themselves as standard benchmarks. However, recent works outline that
relying on a limited collection of datasets is not sufficient to assess the
generalization capability of an approach. In some data-sensitive fields
such as education or medicine, access to public datasets is even more
limited. To remedy the aforementioned issues, we release PyGraft, a
Python-based tool that generates highly customized, domain-agnostic
schemas and KGs. The synthesized schemas encompass various RDFS
and OWL constructs, while the synthesized KGs emulate the character-
istics and scale of real-world KGs. Logical consistency of the generated
resources is ultimately ensured by running a description logic (DL) rea-
soner. By providing a way of generating both a schema and KG in a
single pipeline, PyGraft’s aim is to empower the generation of a more
diverse array of KGs for benchmarking novel approaches in areas such
as graph-based machine learning (ML), or more generally KG process-
ing. In graph-based ML in particular, this should foster a more holistic
evaluation of model performance and generalization capability, thereby
going beyond the limited collection of available benchmarks. PyGraft is
available at: https://github.com/nicolas-hbt/pygraft