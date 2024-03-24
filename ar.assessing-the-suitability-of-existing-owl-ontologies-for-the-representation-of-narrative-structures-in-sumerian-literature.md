---
id: 4rq7bnrndqqm3mn5u7row58
title: >-
  Assessing the Suitability of Existing Owl Ontologies for the Representation of
  Narrative Structures in Sumerian Literature
desc: ''
updated: 1711287996474
created: 1711287996474
---

- url: http://dlib.nyu.edu/awdl/isaw/isaw-papers/7/nurmikko-fuller/
- repo: https://github.com/terhinurmikko/morsul

# Text



This article is available at the URI http://dlib.nyu.edu/awdl/isaw/isaw-papers/7/nurmikko/ as part of the NYU Library's Ancient World Digital Library in partnership with the Institute for the Study of the Ancient World (ISAW). More information about ISAW Papers is available on the ISAW website.

Except where noted, ©2014 Terhi Nurmikko-Fuller; distributed under the terms of the Creative Commons Attribution License
Creative Commons License

This article can be downloaded as a single file
ISAW Papers 7.18 (2014)
Assessing the Suitability of Existing OWL Ontologies for the Representation of Narrative Structures in Sumerian Literature
Terhi Nurmikko-Fuller

Originally a term from the realm of philosophical thought, the label of ‘ontology’ has been adopted and adapted by Computer Science and refers to a formalised structure used for organising knowledge. Together, a knowledge base (a triple store), an ontological structure and a reasoner (software) form an expert system which enables automated inference over a given data set – whilst this is possible without publication via the Web, in doing so, the expert system effectively gains access to an enriched dataset, as further relevant information becomes available from separate external data-streams across the entirety of the Web. This linking of datasets is subject to the same challenges as any equivalent exchange between humans: in order to share knowledge, systems need an effective method of communication. Our task as human experts in charge of data sets is to publish that data in machine-readable, non-proprietary formats, with clear URIs. The adoption of existing ontologies and controlled vocabularies enables the linking of new datasets to existing projects via shared elements such as locations (Pleiades gazetteer1, for example), people (perhaps though projects such as the Berkeley Prosopography Service2) or any other defined, identified element which occurs in more than one dataset.
The tools, the data

Ontologies have played a major role in my on-going doctoral research project, which combines elements from the domain of Semantic Technologies but focuses on Ancient World Data. This work in progress involves issues of Knowledge Representation, Description Logic, Coreference, and its tools are SPARQL, RDF, URIs and OWL. The aim of this research project is to assess the suitability of existing tools for the representation of the ambiguous, incomplete and at times unknown literary narratives that play out within the content of compositions written in the ancient language of Sumerian, and published by the Electronic Text Corpus of Sumerian Literature (henceforth ETCSL)3, an online resource from the University of Oxford, which allows the public free and unlimited access to the lemmatised transliteration and English translation of some 400 composite texts.⬈#p2
Two OWL ontologies

This research project began with an extensive review, and led to the identification and subsequent evaluation of two OWL ontologies thought to be suitable for the representation of cultural heritage data and narrative structures: the CIDOC Conceptual Reference Model (CIDOC CRM)4 and Ontomedia (OM)5. The decision to include the CIDOC CRM was two-fold. Firstly, this event-based reference model is specifically designed as the “semantic glue”6 for linking cross-domain cultural heritage data, and has been implemented by institutions with large cuneiform collections, such as the British Museum.7 Although the ETCSL carries little object data directly, the print, electronic and cuneiform sources for each composite text are listed with each transliteration and serve as potential anchoring points for clusters of RDF triples that would allow the enrichment of the ETCSL data from other sources within Assyriology and the wider Digital Heritage community. Secondly, OM, the second ontology and one designed for the representation of narrative, was purposely designed to link to the CIDOC CRM (Lawrence 2008). Unlike the CIDOC CRM which is one large, all-encompassing structure, OM consists of several interlinking sub-ontologies, amongst which the user-consumer can opt to pick and choose any that bear relevance to their data. OM is essentially an domain-specific upper-level ontology : this oxymoron can be justified if one agrees that the ontological representation of narratives is itself a niche topic but that since OM seeks to be applicable to all fictional narratives (regardless of sub-genre), it can be seen as an example of the class of upper-level ontologies.
mORSuL

The combination of the CIDOC CRM and OM and the addition of a number of specific elements deemed necessary resulted in the creation of mORSuL (the multi-Ontology Representing Sumerian Literature). Thus far, it has been implemented in the Stanford University ontological editor, Protégé8 and serves as part of a proof-of-concept. Preliminary trials with mORSuL have led to two initial conclusions: the ontology is to be extended further to allow for the mapping of bibliographical data as published by the ETCSL (BIBO9 and FRBRoo10 are likely candidates) and the representation of literary tools such as similes, metaphors and analogies. Secondly, the resulting large and complex structure ought to be reduced to contain only those classes and properties which truly match the data available from the ETCSL.
Sumerian humour as an example case study

The next step was to test mORSuL with a case-study example. The chosen composition Three Ox-drivers of Adab is thought to be a humorous one (Alster, 1991-1993; Foster, 1974) and has a narrative structure with repetitive patterns within a frame story – due to the incomplete nature of the latter part of the piece (a result of the fracture and loss of the lower parts of the witness tablets on which the composite text is based) the representation was limited to the first 35 lines only. The composite text as published by the ETCSL is based on the witnesses AO 7739 (TCL 16 80), AO 9149 (TCL 16 83) and CBS 1601.

The story unfolds as follows: There are three friends, all citizens of Adab, who are quarrelling. Unable to solve their dispute, they decide to seek justice and approach the king. They account their story to the king: They are three ox-drivers, one of whom owns an ox, the other a cow, the third a wagon. They became thirsty and suggested that one of them should go and fetch water so that they could all drink. They asked each other, each in turn to go, but all refuse in turn, citing reasons relevant to their possessions: the owner of the ox is afraid it will be devoured by a lion if left unattended; the owner of the cow that his animal will wonder into the desert; the owner of the wagon that the goods will be stolen from it. They agree to all to go together, and in their absence, the ox mounts the cow, the cow gives birth to a calf and the calf eats the load on the wagon. Who, they ask the king, does the calf belong to? The king, unable to provide the solution, seeks the council of a “cloistered lady”, to whom he repeats the story of the ox-drivers verbatim. Sadly, the remainder of the composition which presumably contained the solution to this riddle is fractured and incomplete, and we, the audience, are left in suspense and without closure.
Ontological representation of inscription content

In terms of representing the narrative content via ontological structures, a number of points of interest arise. Although these issues are discussed in greater detail in my thesis (forthcoming), a few examples can be cited to exemplify the types of decisions which need to be made when representing the narrative and the fabula (as defined by Bal, 2009). Firstly, although the events depicted are fictional, the story is set in, or at least refers to, the historical city of Adab (modern Bismaya). The natural laws that govern our reality are applicable to the main ome:Context too (the “reality” in which the story takes place) and at no point is the reader required to suspend their disbelief or encounter entities or events that are magical, supernatural or within a dream. The events as told by the ox-drivers may appear farcical, but are not beyond the remit of plausible realism. The same can be said of the protagonists and their possessions, none of which are supernatural or anthropomorphised.

All the protagonists are considered as instances of omb:Character – they are fictional but can be argued to have a perceivable personality. Each protagonist has at least one unique and definable quality (in the case of the ox-drivers, their possessions) and the bonds of friendship and allegiance are fairly straightforward as is the fall into a dispute (over a given timeline, these omb:Characters who share a positive omb:Alliance bond acquire a negative omb:Enmity). The representation of the ox-drivers’ decision to seek justice is however more complex as is the decision whether to treat it as an instance pertaining to a ome:Social subclass of Legal. It is also worth noting that from the perspective of each ox-driver, they are (presumably) each seeking a decision favourable to themselves and not one which is truly fair. Furthermore, the only account of the events that form the main part of the narrative are the focalised memories of the ox-drivers, and the subsequent retelling of these events by the king, who did not witness them first hand. It may also be argued that the focalised story told to the king is to be seen as an amalgamation of three separate accounts of the events that took place outside the narrative, and the story told to the king is effectively a “composite memory”.
Further work

Research into the representation of Sumerian literary narratives using OWL ontologies continues. The next, imminent stages of the project include the extension and reduction of mORSuL, as well as the addition of data from other Sumerian literary compositions, so that the structure can be queried in terms of intertextuality, reoccurring motifs and possible instances of literary allusions.

Author's note: This research was funded by the Research Councils UK Digital Economy Programme, Web Science Doctoral Training Centre, University of Southampton. EP/G036926/1.
Notes

1 http://pleiades.stoa.org/.

2 http://berkeleyprosopography.org/.

3 http://etcsl.orinst.ox.ac.uk/.

4 http://www.cidoc-crm.org.

5 http://www.contextus.net/ontomedia.

6 http://www.cidoc-crm.org/index.html.

7 http://collection.britishmuseum.org/.

8 http://protege.stanford.edu/.

9 http://bibliontology.com/.

10 http://www.cidoc-crm.org/frbr_inro.html.
Works Cited

Alster, B. (1991-93). "The Three Ox-Drivers from Adab". In Journal of Cuneiform Studies 43-45. 27-38.

Bal, M. (2009). Narratology: Introduction to the Theory of Narrative (3rd Ed), University of Toronto Press.

Black, J.A., Cunningham, G., Ebeling, J., Flückiger-Hawker, E., Robson, E., Taylor, J., and Zólyomi, G. (1998–2006). The Electronic Text Corpus of Sumerian Literature, Oxford. Available at <http://etcsl.orinst.ox.ac.uk/>.

Foster, B. R. (1974). "Humor and Cuneiform Literature". In JANES 6. 69-85.

Lawrence, F. (2008) “The Web of Community Trust Amateur Fiction Online: A Case Study in Community Focused Design for the Semantic Web”, PhD thesis, University of Southampton. Available at: <http://eprints.soton.ac.uk/264704/2.hasCoversheetVersion/thesis.pdf>.

©2014 Terhi Nurmikko-Fuller. Published under the Creative Commons Attribution 4.0 license.

This article is part of ISAW Papers 7.
