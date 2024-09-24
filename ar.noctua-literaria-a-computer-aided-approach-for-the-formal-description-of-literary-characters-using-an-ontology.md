---
id: gqrsnhrlvp3jp8pwdwi4hl5
title: >-
  Noctua Literaria a Computer Aided Approach for the Formal Description of
  Literary Characters Using an Ontology
desc: ''
updated: 1724369188581
created: 1724362626209
---

- https://pub.uni-bielefeld.de/record/2301795
  - https://pub.uni-bielefeld.de/download/2301795/2301798/diss_08_06_08.pdf
- author: @amelie-zollner-weber
- mentions: [[prdct.racer]]
- topices: [[t.humanities.digital]] [[t.story-telling.character]]

## Abstract

In this thesis, an ontology is introduced to model theories for the description and representation of literary characters. Thereby, individual comprehensions of characters by readers are put in focus. To give examples, mostly devil characters derived from different Faust works are described in the ontology. Briefly, several theories of literary characters are combined to create a base of a formal description using an OWL ontology. Here, categories, which describe features and actions of characters mentioned in stories had to be adapted and applied. It is aimed at representing the mental information structure of a reader, which (s)he has in mind when reading a book. Categories describing general aspects of literary characters form the main classes of the ontology, e.g. inner and outer features, actions on subjects and objects. By using sub classes, categories can subsume features of special characters or groups of characters. In addition, so-called instances of the classes represent individual and explicit objects of the domain of literary characters. Here, direct information about a character given in a text is assigned to an instance. Together with the information of the class hierarchy and other instances, a single mental representation of a character is modelled. Different applications have been developed to explore possibilities of the ontology. Even on such a specific ontology, it is possible to apply logic reasoning using Racer and Prolog. But by using these applications, one was faced with problems: queries of logic reasoning can only make implicit information explicit and more individual queries, which cannot be expressed by logic constructs, cannot be retrieved. Nevertheless, one can imagine that logic reasoning is useful for approaches, which intend a usage and retrieval more by machines than by human beings. Furthermore, two applications have been developed to give access to the ontology. A client-server system is introduced to manipulate the ontology, to search and to compare mental representations of literary characters. The system presents a platform for the discussion and access of representations of characters. The inclusion of new subcategories and information about characters as well as different retrievals and comparisons are the core of this system. Results are mostly presented by different visualisations of character representations. This system can support comparisons of literary characters in an essential way. The second application is a method to add semi-automatically instances to the ontology. This approach aims at users well trained in text encoding but who do not have insides into ontologies. In addition, it is worked on reducing the sometimes labour-intensive work of manual insertion of a representation of a character. A TEI encoding scheme was adapted to enable automated parsing of the text and to produce assignments where the different instances might be included into the class hierarchy of the ontology. The user has just to confirm or select a different class. On the basis of derived character representations included in the ontology, the devil characters of the example corpus were analysed and compared to each other taking advantage of the developed client-server system. By using automatically generated histograms of the distribution of instances for certain classes and visualised representations of the characters, it was possible to examine them in detail and to detect similarities and differences. Regarding the literary analysis, a huge development from the first characters until the later ones can be shown. Devil characters become main and modern characters, which means that they can also vary and can be contradictory in their features and motivations. This development takes place independently from the genre. The choice of the genre depends on the single author, but it seems that they each adopted conceptions from different genres. Observed similarities support the assumption of a traditional core of a devil's conception. Although the conceptions vary, it seems that variations are restricted to a specific frame. In summary, one can state that the ontology is an appropriate method to provide structured overviews of characters, observe different representations, and to find information about characters easily, also in the texts, if references are included. By using the mental representations stored in the ontology, it is possible to clarify aspects and to preserve opinions about characters. Although the ontology is restricted in flexible handling of information and can only present things which are included at a particular date, here, it can illustrate mental representations of characters. By using this ontology, the result of a reading process can be shown, but not directly the action of reading and its different states. This approach demonstrates the possibilities and advantages for literature studies if combined with computer-aided approaches.


## Highlights

### Approaches to Description and Classification of Characters

- simple-to-complex
- typical/stereotypical features
- roles of characters concerning the plot 
- by genre
- cognitive-orieted approaches (attaching the process of reading and reception of characters)
  - "Characters are not anymore just the
persons in fiction, but a complex of letters and sense in a reader’s mind."

### Survey of Theories of Literary Characters

- @vladimir-propp’s theory is an important precursor for the perspective known as [[t.humanities.structuralism]]
- @edward-morgan-forster groups literary characters as “flat” or “round”.
  - flat: few features and consisting of a simple structure
  - round: more complex and have more Information
    - can be modified during the plot, so it might be difficult to describe it briefly
- [[t.story-telling.character.greimas-six-actants]]
- @roland-barthes defines general parts of narration, for example functions and indices.
  - functions
are mostly plot related, whereas the indices can refer to characters and their features.
- @manfred-pfister takes different aspects, like the relation between the audience and the characters
in dramas, into account
  - ranks the “dramatis personae”, the
characters, according to general features, like the social status or sex.
  - suggests examining characters in opposition to others
- @jurij-lotman classifies characters as active elements, which carry the plot.
  - By concentrating on oppositional and plot-oriented aspects of characters, other important things might not be taken into account. 
- @fotis-jannidis's approach is based on theories belonging to linguistic and cognitive science oriented literature studies
  - is interested in the process of collecting information from different text sections and arranging them as a unit, which represents a character.
  - features or the actions of a character can be a part of more general problems or patterns. The last aspect comprises the attitude of a reader and the reader steering by a character
  - proposed [[t.story-telling.narratology.jannidis-three-levels]]
  - Jannidis’s approach does not afford a deep categorisation of character features, rather, its value lies on the description of the process by which signals in a story can lead to a detection and collection of attributes

#### A Character Taxonomy (Nieragden)

- @goran-nieragden's approach belongs to approaches that classify character information.
  - refuses approaches that only focus on the role of a character in relation to the plot
- A taxonomy for characters should cover a large range of manifestations of character relevant information and should exceed singular texts and genres.
- Nieragden’s first step is to assume partial similarities between literary characters and real persons.
  - he relates character features and actions
to similar aspects of human beings
- he introduces the net-like system of @helmut-bonheim using four modes: speech, report, description and comment.
  - character information can be divided into a dynamic and a static modes. ^w1fgxgiqobvx
    - Descriptions and comments (“Which characters judge others?”) are regarded as static elements because they do not move the plot further along, and mark stops in the narrated time.
    - The dynamic mode contains speech and reports (“Which characters initiate action?”)
    - The categories are not isolated from each other. For example, a character description given in a speech of a character can belong to more than a single category.
- adopts @seymour-chatman's [[t.story-telling.narratology.chatmans-three-levels-of-narrative]]

### Information Modelling and Representation

- If XML code is directly added to textual data, the data and mark-up can be processed together. 
  - This might be a good solution for modelling for example literary texts and their characteristics like layout and structure. But the mark-up is directed towards the text structure and does not contain a completely different model like a taxonomy or ontology, especially when using suggested annotation schemes like proposed by the [[prdct.text-encoding-initiative-tei]]

#### SUMO

-  one can consider if one can adopt categories of a general ontology like [[prdct.sumo]].
   -  at first sight, one can observe that the category “Abstract” subsumes categories, which contain aspects like “InternalAttribute”
-  Difficulties arise if one tries to add the different activities, e.g. verbal and non-verbal actions of characters
- If one starts mingling categorisations of model theories (for literary characters) with categories of SUMO, one might loose the focus on representing the theories.   
  - For example, one would have to spread character actions over a lot of categories, but a common accepted division into verbal and non-verbal actions of characters like proposed by Nieragden in section 2.4, would not be presented by such an ontology.
    - t.2024.08.22.16 but it could be the basis
- general ontologies don't support the specific tasks and problems of the humanities