---
id: dupappm4t2am3x8bs4oq75e
title: Schema_org
desc: ''
updated: 1701518413576
created: 1701475587999
---

## Overview

- There are three kinds of schema.org term in the schema.org data model: types, properties and enumerated values

## Thoughts

### "reservationFor" rdf:object schema:Thing

- in common language, this property could imply "who is the reservation for" instead of "what is being reserved"
- 'underName' takes a Person or Organization... so I guess you just re-use that property to list all the people. But in a programmatic domain model, you'd use a collection, ideally a typed collection... I guess a weakness of RDF, not schema.org
- what's the point of specifying 'schema:rangeIncludes": { "@id": "schema:Thing" }'

## Style Guide

### Naming conventions

-   Do not give the same name to a type and a property.
    -   Note that schema.org has some legacy cases where this was done in the past. This practice should be avoided.
    -   E.g. Avoid creating both [ContactPoint](https://schema.org/ContactPoint) and [contactPoint](https://schema.org/contactPoint).
-   _Term names should use Singular naming only_, even if the semantics call for a plural.
    -   E.g. [parent](https://schema.org/parent) and not parents, even though for each type, there will always be multiple values for the property [parent](https://schema.org/parent).
-   _Prepositions_ should come after the type or property name.
    -   E.g. [reservationFor](https://schema.org/reservationFor).
-   _Abbreviations_: When creating new types, spell out abbreviations, unless the result is painfully verbose.
    -   Due to legacy entries, sometimes certain words may be abbreviated, or not, in schema.org. Due to lack of consistency, should search for both when looking for a schema term.
    -   E.g. [numTracks](https://schema.org/numTracks) exists in schema.org as a legacy property. If we were creating this property now, it would be _numberOfTracks_ (or better yet, name it _trackCount_ to be semantically aligned with other counting properties).
-   _Spelling_: US spellings must be used.
    -   E.g. [color](https://schema.org/color) and not colour.

#### Thoughts on Naming Conventions

- it's a red flag that types and properties could have the same name. I've grappled with this for [[gd]]... if you're going to say "has <type>", having a separate property seems redundant

## Resources

- https://schema.org/docs/styleguide.html