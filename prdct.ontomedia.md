---
id: twccw0iaye1yncgudxrr8a1
title: Ontomedia
desc: 'goes  beyond bibliographic data, into the discussion of the relationships that exist within and between elements of heterogeneous media'
updated: 1727986625065
created: 1710828459496
---
- url: 
  - https://r4isstatic.com/linkeddata/ontologies/ontomedia/core/expression.owl
  - https://r4isstatic.com/linkeddata/ontologies/ontomedia/ext/common/being.owl 
  - https://r4isstatic.com/linkeddata/ontologies/ontomedia/ext/fiction/char.owl
  - https://r4isstatic.com/linkeddata/ontologies/ontomedia/misc/date.owl
  - https://web.archive.org/web/20160501173107/https://r4isstatic.com/linkeddata/ontologies/ontomedia/
- dead-urls:
  - https://purl.archive.org/domain/ontomedia
    - but references squatted contextus.net :(
- similar: [[prdct.abc-ontology]]
- creator: @faith-lawrence

## Motivation

- The OntoMedia project began as a convergence of three interests - the creation of metadata to describe the content of online amateur fiction, the identification of events in multimedia objects to seed external applications such as sound effects or automatic music generation and, finally, as a potential way of generating narrative
- From that beginning it has expanded to describe narrative in media


## Description

- based on an Entity/Event system
  - provides a natural divide between spatial and temporal information

## Sections

- **Core** The OntoMedia Core consists of three sub-ontologies: Expression, Media, and Space. Expression describes the primary elements of OntoMedia, namely Event and Entity, as well as their subclasses. Media provides binding classes to allow links between pieces of media and their associated Expression objects. Space is an extension of the Signage Location ontology[6], and specifies classes to describe buildings, and regions of both internal and external structures.
- **Extensions** Where Core provides only the very basic classes, Extensions provides more detailed subclasses. This includes Being, to describe people, and a set of Trait classes to define attributes of entities.
- **Events** The Events hierarchy extends the Event class from the Core to provide specialised events. This covers Action, Gain, Loss, Travel, and also additional properties for these extra types.
- **Fiction** In order to provide specialist classes for fiction representation, this set of classes includes Character, which builds upon Being, and other properties to denote spoiler information and accuracy.
- **Media** The Media class in Core only defines a basic MediaItem, so it is necessary to de- fine more detailed classes to describe specific media items. This hierarchy includes audio, image, photograph, textual, and video subclasses.
- **Miscellaneous** Finally, the Miscellaneous set provides classes which may be used by any or all of the other classes. This includes colour information, name representation, and geometry
[[SWOOP|prdct.swoop]]

## Issues

- namespace URI squatted, ontologies not available!?
  - t.2024.10.03.12 found a reference in [[ar.a-comics-ontology]]

## References

- [[ar.ontomedia-creating-an-ontology-for-marking-up-the-contents-of-heterogeneous-media]]
  - has snippets
- [[ar.assessing-the-suitability-of-existing-owl-ontologies-for-the-representation-of-narrative-structures-in-sumerian-literature]]
- [[ar.onto-media-an-ontology-for-the-representation-of-heterogeneous-media]]
- [[ar.onto-media-creating-an-ontology-for-marking-up-the-contents-of-fiction-and-other-media]]
- [[ar.annotation-of-multimedia-using-onto-media]]
- https://www.r4isstatic.com/tag/semantic-weblinked-data-roots