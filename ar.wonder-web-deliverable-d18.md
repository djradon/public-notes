---
id: 8uebjda3bzz5pmg6c23cerv
title: Wonder Web Deliverable D18
desc: ''
updated: 1718135841753
created: 1717703412911
---

- http://wonderweb.man.ac.uk/deliverables/documents/D18.pdf


## Highlights

- OWL is intended to be used as a language for representing and querying ontologies on the Web, and has been carefully designed in order to offer the best possible tradeoff between expressivity and computational efficiency, while guaranteeing at the same time important logical properties such as inferential completeness. The result is a layered logical language allowing for different degrees of expressivity, which is however much less expressive than first-order logic. Using such a language for specifying foun- dational ontologies would be non-sensical: because of their very goals and nature, these ontologies need an expressive language, in order to suitably characterize their intended models.
  - [upper ontology] computational requirements are less stringent, since they only need to be accessed for meaning negotiation, not for terminological services where the intended meaning of terms is already agreed upon.
  - The strategy we have devised to solve this expressivity problem is the following:
    1. Describe a foundational ontology on paper, using a full first-order logic with modality;
    2. Isolate the part of the axiomatization that can be expressed in OWL, and implement it;
    3. Add the remaining part in the form of KIF3 comments attached to OWL concepts.

### Comparing DOLCE, OCHRE, and BFO: The Statue and the Clay

“A statute of clay exists for a period of time going from t1 to t2. Between t2 and t3, the statue is crashed and so ceases to exists although the clay is still there.”

#### DOLCE

- there is a perdurant, the crashing (crash), that lasts during all the period of time (from t1 to t3), and two endurants, the statue (statue) and the clay (clay), which are participants in the perdurant. 
  - More precisely, the crashing is an accomplishment (ACC), the statue is a non-agentive physical object (NAPO), and the clay is an amount of matter (M).
- In DOLCE, endurants have only direct spatial qualities and perdurants only temporal qualities. The temporal regions of endurant and the spatial regions of perdurants are inherited by means of the participation relation 

