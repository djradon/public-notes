---
id: i2asajtvfgt7jfjqggjockm
title: Shex
desc: 'The Shape Expressions (ShEx) language describes RDF graph structures. A shape describes the triples touching nodes in RDF [[!rdf11-concepts]] graphs. These descriptions identify predicates and their associated cardinalities and datatypes. ShEx shapes can be used to communicate data structures associated with some process or interface, generate or validate data, or drive user interfaces.'
updated: 1714763600168
created: 1714755194846
---


- https://rdfjs.dev/shex
- spec: http://shexspec.github.io/primer/ShExJ#schema
- similar: [[prdct.rdf-js.shex]] [[prdct.shacl]] [[prdct.spin]]  ^1vgrpmk2ihl1

## Introduction

ShEx describes RDF graph [RDF11-CONCEPTS] structures as sets of potentially connected Shapes. These constrain the triples involving nodes in an RDF graph. Node Constraints constrain RDF nodes by constraining their node kind (IRI, blank node or Literal), enumerating permissible values in value sets, specifying their datatype, and constraining value ranges of Literals. Additionally, they constrain lexical forms of Literals, IRIs and labeled blank nodes.

## Notation

The ShExJ structure is a sublanguage of JSON. consists of lists and maps of typed objects and values. These are represented as definitions in the following grammar. The content of some constructs involve many choices. These are represented as declarations.

    typeName - a JSON object with a type property with the value "typeName" and the attributes listed to the right of the ":"
    Each attribute is followed by a ":" identifying its type. "[typeName]" identifies a list of objects with a type "typeName". "[type1->type2] identifies a map from type1 to type2.
    declName - a hierarchical representation of choices in the grammar similar to BNF. Declarations don't directly produce JSON objects; instead they capture the possible choices of defined objects or terminals.

## Comparison

### ShEx vs SHACL

- ShEx has the operators | to represent “oneOf” while SHACL has xone to represent exactly one.
- ShEx has been implemented in a variety of programming languages and RDF libraries: Apache Jena, Ruby, Javascript, Haskell, and Python (see section 4.3). In the case of SHACL, most implementations are based on Apache Jena and there is an implementation based on Javascript (see section 5.2) although there are some implementations appearing in other systems like rdf4j. Most ShEx implementations are non-commercial and have been developed mainly by individual projects. SHACL has a mature commercial implementation, bundled with the TopBraid suite of products, which offers a rich user interface for editing SHACL-based data models. Although TopBraid is a commercial product, SHACL’s implementation is based on a separate open source library maintained by TopQuadrant. SHACL is also integrated in the free edition of TopBraid Composer.

#### Schema vs Constraints

- The designers of ShEx intended the language to be like a grammar or schema for RDF graphs. This design was inspired by languages such as Yacc, RelaxNG, and XML Schema. The main goal was to describe RDF graph structures so they could be validated against those descriptions.

In contrast, the designers of SHACL aimed at providing a constraint language for RDF. The main goal of SHACL is to verify that a given RDF graph satisfies a collection of constraints. In this sense, SHACL follows the Schematron approach, applied to RDF: it declares constraints that RDF graphs must fulfill. Just as Schematron relies strongly on XPath, SHACL relies strongly on SPARQL



## References

- https://book.validatingrdf.com/bookHtml013.html