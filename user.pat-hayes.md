---
id: bbdvg6xsnb5utkj9xrea2dg
title: Pat Hayes
desc: ''
updated: 1728140172695
created: 1728140111005
---

## Re: RDF 2 Wishlist

On Nov 1, 2009, at 11:51 AM, [[user.sandro-hawke]] wrote:

> So, what should W3C standardize next in the area of RDF, if anything?
> OWL 2 added a bunch of stuff to OWL that users wanted and implementors
> were willing to tackle.  Are there things like that around RDF?

Well, I just used the invited talk to give my speech on this topic,  
but here's a more concrete list. I reserve the right to think of more  
tomorrow.

1. Clean up and simplify RDF abstract syntax. Literals can be  
subjects, properties can be blank nodes, etc. In fact, anything can be  
anything in the triple space, in the conceptual graph model. The  
existing semantics can handle this without change. The spec gets to be  
shorter and easier.
1a. All literals are typed, plain literals are understood in  
retrospect to be an abbreviation for typing with rdf:text.
1b. If XMLLiteral is necessary, make it into an ordinary datatype. Or  
get rid of it altogether.

2. A better syntax than RDF/XML. I also like turtle or N3 style, but  
whatever, striped syntax is just too remote from the actual graph  
model to be useful, and it imposes subtle and harmful influence over  
the whole language (eg it was why we don't have literals as  
subjects.)  FWIW, this is likely to be the hardest problem for  
backward compatibility, I suspect. I wonder how hard it would be to  
have a converter from RDF/XML into some other form, as a W3C service?

3. Add a scope mechanism to the syntax, along the lines of the  
'surfaces' idea in my talk. (Terminology and exact syntax for this can  
be adjusted to suit, but parentheses work well :-) This is an  
extension to the current model, existing RDF documents are understood  
to be on a document-level surface that was always there. As well as  
making bnodes respectable, this provides a clean foundation for a  
whole lot of other things, including:
3a. named surfaces (aka named graphs)
3b. negation (see my ISWC talk) and hence full FOL as a natural and  
well-understood extension (without any retro changes to existing RDF)  
This is close to my heart, but not of immediate priority: Im more  
concerned that nothing is done which would break this as a future  
pathway.
3c. NAF negation. I didn't go into this in the talk, but the big  
problem with any kind of nonmon reasoning on the Web is that nonmon  
(notably NAF) only works inside fixed boundaries, and so far we don't  
have a way to draw the boundaries. Scoped surfaces give us this, and  
so we could have for example 'closed' surfaces which support NAF  
reasoning, and the whole logic can then be monotonic. Best of both  
worlds, and IMO a better solution that the RIF idea of multiple  
logical 'zones' with conflicting semantics. Though it would be  
straightforward to link it to the RIF spec, I am pretty sure (the idea  
would be, for RIF, that it takes its logic-zone cue from the 'color'  
of the surface it finds the rules on. All written in RDF, of course :-)
3d. Named surfaces provide better mechanism than reification for RDF- 
metadata-of-other-RDF (It is token level rather than abstract graph  
level, which suddenly makes sense.)
3e. Cleaner model for such things as unasserted annotations in OWL,  
use of RDF collections to encode OWL syntax, etc.., where some of the  
RDF isn't really being, like, asserted, exactly.

4. Deprecate RDF reification, containers.

5. (related to 4) Choose a recommended way to encode n-ary relations,  
explain it fully, and deprecate all the others. Or, generalize RDF  
triples to n-tuples syntax, with the previous as a backward  
compatibility hack for old RDF.

6. Build a clean version of SKOS into RDF, to replace RDFS. Current  
RDFS is then OK but deprecated in favor of translation into newer  
vocabulary, eg you should actually say that you want subclass/property  
to be transitive, when you do. In the semantics, this is done by  
changing various 'iff's to 'if's, making reasoning searches easier.

7. Include a modern, nuanced version of owl:imports into RDF. Should  
be possible to import only a part of a large ontology.

8. Related to 6 & 7: provide some vocabulary and guidance for how to  
link RDF data without falling into the owl:sameAs black hole. Note, we  
won't completely solve this, but even a beginning would be a huge  
improvement over the current situation, and this should be done at the  
RDF level rather than a forest of conflicting conventions growing into  
use.

9. Provide some way (an RDF vocabulary?) to support versioning,  
deprecation, etc., if only some best practice recommendations.

Pat