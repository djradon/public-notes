---
id: onf6e2kcaralhmgleu7k8ys
title: Summary Un Asserted
desc: ''
updated: 1720553730349
created: 1720553570464
---


Hi Thomas,

First, I agree with everything Peter wrote in his (first) reply. (Though, regarding names and definitions, I might put it as: triples as objects (triple terms) simply denote relationships (so we can refer to them directly), whereas triples in graphs simply assert that they hold.)

Again, you talk about "unasserted assertions", as if referring to a triple (term) is somehow affected if that is also asserted (or is not). There is no such interaction a priori, so I don't see the problem with the reifier in "1/4". It appears totally abstract and does not relate to any notion of truth; it is not "about an unasserted assertion". It is simply relating to what `:s :p :o` means, i.e. the abstract relationship. If what you want is an opaque context, just use a literal with an RDF serialization. If it is about an entity in your domain which reifies falsehoods (like a Myth), it would itself be proven at odds with a world in which those relationships actually hold. That's pretty much the point of referring to relationships, so that you then have something to check if it's true or not. (And monotonicity is not violated here.)

Still, I may understand parts of your discomfort, in *some* cases. I think you might sense a distinction in "nature" between kinds of reifiers which mediate what needs to be true for the reifier to "make sense" (such as a Purchase), and others which *only* refer to relationships, true or not (such as a Claim).

But there is no need to add this distinction in the reifying relationship. It is enough to specify the appropriate `rdf:type` of the reifier.

If you have a simple relationship:

    <Alice> :bought <SomeComputer> .

And a reifier which `rdf:reifies` that:

    <purchase1> a :Purchase ;
        :date "2014-12-15"^^xsd:date ;
        :seller <ComputerStore> ;
        :cost 2500 ;
        :currency :USD ;
        rdf:reifies <<( <Alice> :bought <SomeComputer )>> .

Then the only additional thing needed in RDF 1.2 is to ensure that a triple term entails something understandable by a reasoner, like a classic reification token:

    <purchase1> rdf:reifies [ rdf:subject <Alice> ; rdf:predicate :bought ; rdf:object <SomeComputer> ] .

(This has been suggested (as "T-entailment"?). I'm convinced that it is a critical requirement for interoperability (or some variant thereof, such as an rdf:Relationship subclass of rdf:Statement).)

I think what bothers you is that it would reasonably make sense to say that in this case, given the intuitive meaning of a Purchase, the simple `:bought` relationship should also hold (i.e. that triple should be entailed). And I agree, for this specific case. Not for the general use of `rdf:reifies`.

Specifically then, we want to say that IF something is a :Purchase which rdf:reifies a :bought relationship between ?x and ?y, THEN ?x :bought ?y.

And we don't need anything more for that. This is already possible using OWL.

We first need a "rolification" property for the :Purchase (that's just an existing "OWL trick", to be able to use class memberships in property chains):

    :Purchase rdfs:subClassOf [ owl:onProperty _:RolifiedPurchase ; owl:hasSelf true ] .

And a class for the :bought relationship, which is additionally tied to a "rolified" property:

    _:BoughtRelationship owl:equivalentClass [ owl:onProperty rdf:predicate ;
                                               owl:hasValue :bought ] ;
        rdfs:subClassOf [ owl:onProperty _:RolifiedBoughtRelationship ; owl:hasSelf true ] .

Then we can define subproperty chain axioms as needed:

    _:boughtRelation rdfs:subPropertyOf rdf:reifies ;
        owl:propertyChainAxiom (_:RolifiedPurchase rdf:reifies _:RolifiedBoughtRelationship) .

    :buyer rdfs:domain :Purchase ;
        owl:propertyChainAxiom (_:boughtRelation rdf:subject) .

    :item rdfs:domain :Purchase ;
        owl:propertyChainAxiom (_:boughtRelation rdf:object) .

From this it is entailed that `<purchase1>` is a full-fledged N-ary relationship:

    <purchase1> a :Purchase ;
        :date "2014-12-15"^^xsd:date ;
        :buyer <Alice> ;
        :seller <ComputerStore> ;
        :item <SomeComputer> ;
        :cost 2500 ;
        :currency :USD .

And from that, is it easy to define a chain axiom to the simple relationship:

    :bought owl:propertyChainAxiom ( [ owl:inverseOf :buyer ] :item ) .

So that this is entailed (asserted):

    <Alice> :bought <SomeComputer> .

This is something the used ontology can define, to clarify the "intuitions" on the Purchase class, and also mechanically aid in data interoperability. Not all reifiers (such as data provenance / editorial management) have this "nature", so it should really be up to how the type of the reifier is defined. Which the above proves is already possible.

To see that this works, try it out in an OWL tool such as the OWL-RL reasoner, which is also online courtesy of the Finnish National Library at [1]. That example link uses the example data above, which I put in a gist at [2]. (In that gist there is also a version where the `:seller` is not directly asserted, but `<purchase1>`  instead also reifies `<Alice> :shoppedAt <ComputerStore>`, and rules are added so that the `:seller` and `:shoppedAt` triples are entailed.)

Aside: I think it is imperative that reifiers like `<purchase1>` are recognized, as shown above, as standard N-ary relationships. A lot of the *seemingly* simple triple annotations we've seen appear to be of that kind, in "disguise" (just a piecemeal description of). And N-aries are a common kind of relationship reification *not* limited to the rather narrow "triple token" notion informally defined in RDF. Specifically, the Purchase class is a kind of reifier known as a relator [2], which mediates the buyer, item, and seller, date, cost, currency. Which I think at least Enrico has been saying all along.

So with `rdf:reifies`, transparent triple terms as objects, and the addition of a simple "T-entailment", we appear to already have all pieces required to cater for the use cases we have deemed reasonable, including ones where reified relationships should also be entailed to hold. With ontology-powered systems, they mighn't need triple terms to begin with. But the annotation syntax is a practical convenience for lots of real world systems, where the above OWL usage is far from prevalent today, or where other concerns are more pressing. As shown above, semantically, OWL has what is needed to make all approaches interoperable. (And a lot more is available, such as cardinality restrictions).

Best regards,
Niklas

[1]: <https://www.ldf.fi/service/owl-rl-reasoner?text=&source_1=https%3A%2F%2Fgist.githubusercontent.com%2Fniklasl%2F69428b043be6f1d33fd45f89cbe52632%2Fraw%2Fb3352d9648dc7710d7128af6ac731464f54ba836%2Fpurchase-entailments.ttl&iformat=turtle&format=turtle&fullClosure=no&owlClosure=yes&rdfsClosure=yes&owlExtras=yes&axioms=no&daxioms=no>
[2]: <https://gist.github.com/niklasl/69428b043be6f1d33fd45f89cbe52632>
[3]: <https://ontouml.readthedocs.io/en/latest/classes/sortals/relator/index.html>



On Tue, Jul 9, 2024 at 4:50 PM Thomas Lörtsch <tl@rat.io> wrote:
>
>
>
> Am 9. Juli 2024 16:07:25 MESZ schrieb "Peter F. Patel-Schneider" <pfpschneider@gmail.com>:
> >There are much better names than "Unasserted assertions", largely because it is unclear just what "assertion" means and later examples bias its meaning. I see two choices for "assertion" - "embedded triple" or "triple occurence", where the difference is that there is precisely one embedded triple for a combination of subject, predicate, and object but there are multiple triple occurences for a combination.
>
> Assertion, the way I try to define it, refers to a triple, or fact, in a graph. The unasserted assertion, as I said, equals the subject of an RDF standard reification quad. However, just speaking of "facts/triples" and "statements" would most probably not convey the difference in meaning that this discussion centers around.
>
> >PROBLEM 1:   This is just yet another example of the problem with the "seminal example".   If you want to be able to have separate views of a triple then you have to somehow be able to create separate resources that all somehow refer to the triple.  The working group has already what appears to be a widely-acceptable proposal in this area with both a special prediate - rdf:reifies - and shorthand syntax for Turtle.   So this problem is already solved.
>
> This problem is not solved, as IMO my extremely concise example below clearly shows. Please provide a counter example to prove your point.
>
> >PROBLEM 2:  This is just yet another complaint about the verbosity of RDF. RDF is indeed verbose (or lacking and thus requiring verbose encoding) for many things - node names, n-ary predicates, literals, lists, sets, alternatives, universals, disjunctions, modals, etc.  Adding some sort of special facility to the core of RDF to overcome this verbosity makes the core of RDF more complex, harder to implement, and probably harder to understand. So, yes, the verbosity of RDF is a problem but reducing verbosity comes at the decided cost of increased complexity.
>
> This is a discussion long resolved and the resolution was to set up this working group and have it define an easy way to make statements about statements. I think everybody is aware of the complexity that adds under the hood.
>
> >PROBLEM 2 and 3:  A way of getting around verbosity is shorthand syntax.  This has been in Turtle for quite some time, reducing the user-perceived verbosity of several aspects of RDF, particularly lists.   N-triples, of course, does not include shorthands but the fundamental design principle of N-triples is simplicity.  The working group has what appears to be a widely-acceptable proposed shorthand syntax for the common case of an asserted triple with qualifiers, covering by-and-large the LPG and Wikidata.   The shorthand syntax can also be used when querying, in many cases completely eliminating the need to see the expanded version.   There are some aspects of this shorthand that could be improved and there is a proposal already put forward to the working group on this.
>
> Problem 3 is not so much about syntax but about how reification is not the right approach to all those use cases that qualify assertions.
>
> >PROBLEM 4:  Turtle should be the only syntax that most users, particularly naive users, see.  Tools designed to produce RDF that users see should produce Turtle output and Turtle output that uses the shorthand syntax whereever possible.  Tools that perform differently are to be avoided.  But this is only a small part of the problem of producing readable output for any graph-based structure.  There are few tools that do this in a way that is even somewhat close to acceptable and no tools that I am aware of that do a great job for graphs of any size.  The problem is just very, very, very hard (and probably impossible due to the limited sensory and cognitive capabilities of humans). I would love to be proved wrong and have access to a tool that would provide a usable view on Wikidata for me, even just the ontology part.  In any case, lines of characters is the wrong format for just about all people to see RDF graphs of any size.
>
> The importance of N-Triples as the only syntax that really counts in implementation, has been stressed in WG meetings many times. Streaming contexts were mentioned as wasvexchsnge of fata over the wire. I was even asked to provide examples for the Nested Named Graphs proposal in N-Triples instead if TRIG. The different syntaxes should be equally expressive, or what was seemed to conveyed in a shorthand notation gets lost when transmitted over the wire.
>
> >In summary, I don't see anything in these problems that have either not been already addressed or are not a true problem at all.  That being the case, why should I bother to examine a proposal that doesn't address anything that has not already been adddressed.   New proposals should build on already-existing work of the working group, using the deliberations that have already been performed and the nomenclature and solutions that have already been proposed, and comparing the new solutions to them.
>
> In summary you make claims that are not substantiated ("solved") and you argue that if only the world was organized differently, the problems I describe would go away. The latter is not going to happen, the former would need a concrete example to be plausible.
>
> I maintain that with the current proposal it is impossible to annotate an unasserted assertion (equal to the subject of an RDF reification quad) AND have that same statement as a fact in the same graph. However, that has repeatedly been claimed to be a use case that we need to address. So, imo we clearly have a problem. And basing the occurrence semantics on  reification instead of instantiation is another problem and my proposed solution solves both in combination.
>
> Best,
> Thomas
>
> >peter
> >
> >
> >On 7/9/24 06:43, Thomas Lörtsch wrote:
> >> Hi all,
> >>
> >> as promised in the last WG meeting almost two weeks ago this is a summary of the issues I see with "unasserted assertions" and a proposal of how to resolve them and, in the same stroke, some other problems as well.
> >>
> >>
> >>
> >> DEFINITION
> >>
> >> "Unasserted assertions" - for lack of a better name - means statements that are described (and probably annotated), but are not contained as facts in the graph. I.e. those statements are talked about, but not endorsed. RDF standard reification is a construct to such effect: the reification quad describes a statement, but it doesn’t entail it.
> >>
> >>
> >> PROBLEM 1/4
> >>
> >> Both CG and WG repeatedly and explicity maintained that RDF-star needs to support "unasserted assertions". However, the way that RDF-star currently implements them is ambiguous, lossy and non-monotonic even. It relies completely on the absence of a fact from the graph. If however that fact is present, it is no longer possible to talk about it as refering to something unasserted.
> >>
> >> For example, we may want to document and comment on a statement without endorsing it. We write
> >>
> >>      << :s :p :o >> :a :b .
> >>
> >> If however that same statement is also to be part of the graph, for whatever reason, like so:
> >>
> >>      << :s :p :o >> :a :b .
> >>      :s :p :o .
> >>
> >> there is no way to express that the annotation is meant to refer to an unasserted statement.
> >> There are many situations in which this problem might occur: we might want to document different viewpoints or versions, graphs might be merged or updated, adding the fact, etc.
> >>
> >>
> >> PROBLEM 2/4
> >>
> >> As a way out of this problem I discussed to require another statement describing if an annotation is meant to annotate an unasserted assertion, like so:
> >>
> >>      << :s :p :o >> :a :b ;
> >>                     a rdf12:UnAssertedAssertion .
> >>      :s :p :o .
> >>
> >> However, this is not a valid solution, because a second problem runs even deeper: the meaning of triple terms is defined as reification. Because of those reification semantics a triple term is always unasserted. By consequence we would rather need to add a statement whenever we intend to anotate a statement that we actually assert, like so:
> >>
> >>      << :s :p :o >> :c :d ;
> >>                     a rdf12:AssertedAssertion .
> >>      :s :p :o .
> >>
> >> In practice this would add considerable load as most annotations will aim to annotate facts in the graph, not e.g. some unendorsed viewpoints. This would also require more effort when querying.
> >>
> >>
> >> PROBLEM 3/4
> >>
> >> On the plus side the approach in 2/4 could be considered to be very expressive as the actual fact would now be completely independent from any annotations, on asserted and unasserted assertions alike, adding a new degree of expressivity. However, for many use cases this separation is rather a problem than a feature, because they ask for a clear and solid connection between a fact and "its" annotation. All use cases of qualification fall in this category, e.g. Wikidata, LPG, and many more. OTOH, for use cases that aim to annotate statement with rather orthogonal aspects like provenance, refication is the right choice. So just changing the underlying semantics from one to the other is not a solution. We rather need both.
> >>
> >>
> >> PROBLEM 4/4
> >>
> >> The shorthand syntax by intuition provides a solid link between a stated fact and its annotation. However, no other syntax does that, so an unassuming user's intuition is betrayed when the data is serialized to e.g. N-Triples. This is a serious usability problem.
> >>
> >>
> >>
> >> PROPOSAL
> >>
> >> To properly support unasserted assertions, and to solve the semantics problems in the same stroke, let's bite the bullet and define two primitives instead of one:
> >> - an unasserted triple term occurrence with a semantics of reification
> >> - an asserted triple term occurrence with a semantics of instantiation
> >> Define those primitives and their semantics not in the abstract syntax, but via the two properties rdf12:reifies and rdf12:instantiates.
> >>
> >>
> >> Abstract Syntax:
> >>
> >> graph      ::= triple*
> >> triple     ::= subject predicate object
> >> subject    ::= iri | BlankNode
> >> predicate  ::= iri
> >> object     ::= iri | BlankNode | literal | tripleTerm
> >> tripleTerm ::= triple
> >>
> >>
> >> Properties:
> >>
> >> To provide the user facing triple term occurrences with their respective semantics (un-/asserted etc) we explicitly (and normatively) define two properties, with different semantics, to be used with abstract triple terms as their rdfs:range:
> >> - rdf12:reifies defines a reification of an abstract triple term
> >> - rdf12:instantiates defines an instantiation of an abstract triple term
> >>
> >> A reification via rdf12:reifies doesn’t assert the statement described by the triple term, it merely provides an identifier to refer to an occurrence (whereever, whenever) of it. IIUC that is exactly what we have now. A mapping to RDF 1.1 clarifies that:
> >>
> >>      :r_1 rdf12:reifies <<( :s :p :o )>> .
> >>
> >> in RDF 1.1 would be expressed as
> >>
> >>      :r_1 rdf12:reifies [
> >>          rdf:subject :s ;
> >>          rdf:predicate :p ;
> >>          rdf:object :o .
> >>      ]
> >>      rdf12:reifies rdfs:range rdf:Statement .    # axiomatic triple
> >>
> >> An instantiation via rdf12:instantiates OTOH does indeed assert the statement it annotates, in addition to providing an identifier to annotate that assertion. To make the connection between statement and annotation direct and solid, but not break the set semantics of RDF, the model and semantics mimick the singleton property approach. A mapping to RDF 1.1 clarifies that:
> >>
> >>     :i_1 rdf12:instantiates <<( :s :p :o )>> .
> >>
> >> in RDF 1.1 would be expressed as
> >>
> >>      :i_1 rdf12:instantiates [
> >>          :s :p_1 :o .
> >>          :p_1 rdf12:instantiatesProperty :p .
> >>      ]
> >>      :s :p :o .
> >>      rdf12:instantiatesProperty
> >>          rdfs:subPropertyOf rdf:type .           # axiomatic triple
> >>
> >>
> >> Macro:
> >>
> >> An instantiation always entails the triple term, ':s :p :o' in the above example. This is defined as a macro when mapping between concrete syntaxes.
> >>
> >>
> >> Concrete syntaxes:
> >>
> >> I see two possible approaches. One is to not change the currently defined syntaxes, but let the shorthand syntax express instantiation, and let the standard syntax express reification. That would align syntaxes as they are defined right now with the intuitions they support, but all modifications would happen "under the hood" - e.g.:
> >>
> >>      :s :p :o  {| :a :b |}      # rdf12:instantiates, asserted and annotated
> >>      << :s :p :o >> :d :e .     # rdf12:reifies, not asserted but annotated
> >>
> >> Another approach would be to let instantiation be expressed with double chevrons and reification with triple chevrons, e.g.:
> >>
> >>      << :s :p :o >> :a :b.      # rdf12:instantiates, asserted and annotated
> >>      <<< :s :p :o >>> :d :e .   # rdf12:reifies, not asserted but annotated
> >>
> >> The first approach, based on the current syntaxes, does more clearly disambiguate the two modes of expression, but it also adds more "unrest". The second approach stays closer to the orignal RDF* proposal and is more uniform. The second approach might enable a more usable query interface, e.g.:
> >>
> >>      ?s ?p ?o                   # asserted
> >>      << ?s ?p ?o >> ?a ?b       # asserted and annotated
> >>      <? ?s ?p ?o ?> ?a ?b       # asserted and optionally annotated
> >>      <<< ?s ?p ?o >>> ?a ?b     # unasserted and annotated
> >>      <<? ?s ?p ?o ?>> ?a ?b     # (asserted or unasserted) and annotated
> >>      <?? ?s ?p ?o ??> ?a ?b     # (asserted or unasserted) and optionally annotated
> >>
> >> Occurrence identifiers are omitted in all examples, as they don’t differ from the current proposal. Likewise the mapping to N-Triples doesn’t change, except from the introduction of a new property, rdf12:instantiates.
> >>
> >>
> >>
> >> DISCUSSION
> >>
> >>
> >> In principle:
> >> RDF is an Open World technology, designed to facilitate decentralized authoring and integration of data and we can’t rely on the absence of statements to convey meaning (e.g. unassertedness or non-endorsement). Out-of-band arrangements in concrete application may be more specific, but we can not make any claims based on that (and "RDF-star supports unasserted assertions" would be such a claim).
> >> I’d like us to go the extra mile and adopt the above proposal: implement two different kinds of annotation primitives. This also opens the road to a future with more elaborate constructs like quoted versioning.
> >> I could also live with a scaled down reference to the support of unasserted assertions, on the lines of "you can emulate a surrogate support for unasserted assertions like this, but be aware that the construct easily breaks in practice if not tightly controlled".
> >> However, that would still not solve the other problem, namely that reification is not the right formalisation for most of our use cases.
> >>
> >> Properties:
> >> defining the semantics of triple term occurrences via the properties rdf12:reifies and rdf12:instantiates is a modification of the mechanism introduced by the TEP proposal in the RDF-star CG report.
> >>
> >> Instantiation:
> >> There are different names for the underlying concept. It can also be understood as a form of n-ary relation where the instance-type relationship is modeled via a blank node. So the term "instantiation" refers to its most theoretical aspect (which best mirrors "reification", and that’s why I chose it in this summary), "n-ary relation" would refer to the way of modelling it, and yet another term "qualification" would emphasize the meaning of the construct. "Singleton properties" is a term that I try to avoid because the proposal has been met with so much resistance, but it is a concrete implementation of the same concept. I provide a very singleton property like mapping to RDF 1.1 above, but slightly different mappings could provide better computational properties, e.g. letting the object refer to the singleton, resulting in better indexing and join performance.
> >> However, what is most important to me is that the qualifying annotation, by being attached to the instantiation, is unmistakeably annotating a statement that is actually asserted in the graph. The only metaphysical baggage involved is the definition of what a type-instance relation is, and that should be uncontroversial.
> >> Defining the relation between annotated thing and annotating thing not as a subproperty-relation but as a type-instance-relation follows the idea that those annotated relations are not meant to be annotated any further (that too is possible, but not the norm). So they represent leaves of an inheritance tree rather than knots. In OO tradition leaves are understood as instances, whereas knots would be defined as sub-properties.
> >>
> >> Mappings:
> >> The mappings to RDF 1.1 are provided for two reasons:
> >> - clarify the meaning of new constructs in terms of well-known ones
> >> - provide a path to backwards compatability.
> >> RDF-star implementations should not be required to support them on the implementation level.
> >>
> >> Many-to-many:
> >> The astute reader will have noticed that both mappings to RDF 1.1 are many-to-many. However, owing to the semantics inherent in instantiation, this is a kind of many-to-many relationship that only properly supports co-denoting statements. A common instantiator for :Car and :MotorizedVehicle makes sense, whereas for conceptually very different entities like :Car and :Person it mostly does not. Such a semantics remains true to the integration focus of RDF, but also caters to the more focused approach of LPG. Reification on the other hand rather refers to the statement(s) as a whole, as an entity in their own right. This caters well to use cases that explicitly don’t want to qualify statements but that that try to keep a safe distance between statement and annotation, e.g. provenance and other orthogonal concerns.
> >>
> >> Querying:
> >> Do we currently allow to query for the abstract triple term <<( … )>> or do we plan/have to do so? If yes, that might be a better replacement for the last option above: <?? … ?>>. In any case the above proposal is just a sketch and may not even be helpful. I’m not good at querying.
> >>
> >> Abstract triple:
> >> People can use the abstract triple term as object of whatever statements they like. They are on their own with such freewheeling usage, as no other semantics are defined in the spec than those of rdf12:reifies and rdf12:instantiates. However, this may lead to some fruitful experiments, e.g. with referentially opaque triple terms, and it stays in the spririt of RDF being a pretty open technology.
> >>
> >> Fragment identifiers:
> >> Reification defines a handle to address the whole triple as an object, instantiation rather defines a handle to address the predicate of the triple. Therefore an annotation on a reifier annotates the whole triple as an object, an annotation on an instantiator rather qualifies the relation itself. Both arrangements are not set into stone, and adding more specific properties to explicitly annotate and qualify the subject, predicate, object or whole triple (or a set thereof) may be defined. The RDF reification vocabulary might be reused to that end, but defining a new set of properties seems to be the safer approach. Such properties may be applied to reifications as well as instantiations (and there are use cases for both).
> >>
> >> Merging and temporal aspects:
> >> It was argued that the problems outlined above are not actual problems for us but related to issues outside of RDF-star, i.e. merging is not an issue for RDF-star and temporal aspects are not considered in RDF at all. I disagree with both accounts: RDF is a technology focused on decentarlized data integration. Such integration requires merges, and it leads to the addition of statements in existing graphs. In both cases the situation may arise that a statement that was annotated but not endorsed is added as an actual fact. Then what was meant to be unendorsed suddenly is endorsed. Problems with other use cases, like representing different viewpoints, notwithstanding.
> >>
> >>
> >>
> >> Best,
> >> Thomas
> >
>
