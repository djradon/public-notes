---
id: d8aw6cyckgkgoan59otg79h
title: Lrmoo
desc: 'Library Reference Model object-oriented'
updated: 1724267612691
created: 1724261615741
---

- https://cidoc-crm.org/extensions/lrmoo/owl/1.0/LRMoo_v1.0.owl
- extends: [[prdct.cidoc-crm]]
- related: [[t.library-science.work_expression_manifestation_item]]

## Description

- LRMoo is strictly an extension of CIDOC CRM and cannot be implemented without using key classes and properties from CIDOC CRM.

## Highlights

- [[t.library-science.work_expression_manifestation_item]]
- Nomen (F12) comprises associations between an instance of any class, and signs or arrangements of signs that are used to refer to and identify that instance
  - Signs include alphanumeric characters, ideograms, notations such as chemical structure symbols, sound symbols, etc
  - Spelling variants are regarded as different nomens, whereas the use of different fonts (visual representation variants) or different digital encodings do not change the identity
  - An arbitrary combination of signs or symbols cannot be regarded as an appellation or designation until it is associated with something in some context. In that sense, the F12 Nomen class can be understood as the reification of a relationship between an instance of E1 CRM Entity and an instance of E41 Appellation
  - Two instances of F12 Nomen can happen to be associated with equivalent strings and yet remain distinct, as long as they refer to distinct instances of E1 CRM Entity
    - Furthermore, two instances of F12 Nomen referring to the same instance of E1 CRM Entity may be associated with equivalent strings, and remain distinct as long as they are associated with distinct properties of the F12 Nomen class (for example, having the same spelling in different languages, or being defined in different controlled vocabularies).
- has_member (R10i) and E28 Conceptual Object
  - associates an instance of F1 Work with an instance of E28 Conceptual Object that represents a generalization of the work. The property can be used to group variant, alternative or related works that are considered to share a common concept.
  - Whereas instances of F1 Work are always realised in instances of F2 Expression, there is no particular expression that fully conveys the instance of Conceptual Object that a work may be a member of.
  - Intended usage of the property includes what is discussed as 'superwork' in the library community. Typical examples are novels that can be grouped by fictional universes or common characters, paintings or graphical works that exist as a family of alternatives, musical compositions that are referred to as the same although they exist as particular versions that are each identified as an individual work.
- F18_Serial_Work 
  - The retrospective reprinting of all issues of a Serial Work at once, in the form of a monograph, is regarded to be another member of the F1 Work, which contains the Serial Work and the Work realised in the monograph. This does not make the monograph part of the Serial Work.

## References

- https://www.cidoc-crm.org/frbroo/home-0
- https://ontome.net/namespace/217
- https://journal.code4lib.org/articles/16491