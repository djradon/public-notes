---
id: grnxd8eu85x0cx2akmwmnbu
title: Guidelines for Writing Definitions in Ontologies
desc: ''
updated: 1724601672774
created: 1724600995008
---

- https://philpapers.org/archive/SEPGFW.pdf
- authors: @selja-seppaelae @alan-ruttenberg @barry-smith 

## Abstract

Ontologies are being used increasingly to promote the reusability of scientific information by allowing heterogeneous data to be integrated under a common, normalized representation. Definitions play a central role in the use of ontologies both by humans and by computers. Textual definitions allow ontologists and data curators to understand the intended meaning of ontology terms and to use these terms in a consistent fashion across contexts. Logical definitions allow machines to check the integrity of ontologies and reason over data annotated with ontology terms to make inferences that promote knowledge discovery. Therefore, it is important not only to include in ontologies multiple types of definitions in both formal and in natural languages, but also to ensure that these definitions meet good quality standards so they are useful. While tools such as Protégé can assist in creating well-formed logical definitions, producing good definitions in a natural language is still to a large extent a matter of human ingenuity supported at best by just a small number of general principles. For lack of more precise guidelines, definition authors are often left to their own personal devices. This paper aims to fill this gap by providing the ontology community with a set of principles and conventions to assist in definition writing, editing, and validation, by drawing on existing definition writing principles and guidelines in lexicography, terminology, and logic.

## Highlights

- a definition has 
  - intention (with its counterpart-in-reality, extension)
  - form (i.e., the text and maybe accompanying axioms)
- canonical form: "X is a Y that Zs"
  - Y is genus, i.e., what kind of thing
  - Z is differentiae/distinguishing features
- In ontologies, definitions include
**necessary conditions** that apply to all the members
of the extension, but which may also apply to
members of other term extensions, and, whenever
possible, jointly **sufficient conditions**, which allow
a user to determine whether a given entity is a
member of the extension