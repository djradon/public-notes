---
id: Zky5xjNTxp2PENk30AyVs
title: RDF Turtle
desc: Terse RDF Triple Language
updated: 1713368384900
created: 1635703038494
---



- [[p.hasSpecification]] https://www.w3.org/TR/turtle/


## Pros

-   **Turtle is the Language of the Semantic Web.** There have been, over the years, a fair number of different representations of semantics, some very minimal (n3), some tied into the rdfs model (XML-RDF), some using different functional representations such as Manchester notation. Yet none of them have achieved the adoption of Turtle within this space by those who have focused on using RDF as a descriptive framework.
-   **Turtle Underlies SPARQL, SHACL and other languages.** The Turtle language informed the shape of SPARQL, SHACL and many other RDF stack languages, and as such has become something of a unifying linguistic design.
-   **Turtle is Human Readable.** In so far as any data serialization format is human readable while at the same time being terse (indeed, it is more compact than JSON while simultaneously being more precise). It should be noted that the Terseness of JSON vs. XML was one of the primary reasons that developers walked away from the XML toolset in favor of JSON. However Turtle is even terser, while still being able to be more expressive than the JSON language.
-   **Turtle Is A True Streaming Language.** JSON ironically suffers much the same issue with regard to streaming that XML does – when you transport JSON, before you can do anything with it you have to reparse it. If the JSON structure is larger, you have to wait until you reach a nature breakpoint (the end of an array or object definition). Turtle, on the other hand, is normalized, which means that the functional parsing boundary for Turtle typically is far smaller than it is for JSON. This in turn translates into the ability to load content into the database considerably faster, and in many cases to perform validation against _existing_ data, meaning that Turtle is a natural language for master data management.
-   **RDF automatically deduplicates.** JSON, because it is a denormalized structure, implicitly requires that duplication exists. RDF in general and Turtle in particular, are representations of content that will end up in a triple store index, and the index need only make an assertion about a given statement once. This makes queries very fast, considerably faster than can be achieved with JSON, especially when powered by Graph Processing Units (GPUs) for parallel processing. JSON gains no real advantage when parallel processing is involved.
-   **Turtle is unambiguous, JSON is not.** JSON-LD emerged as a standard to work with the semantic web, but it currently has four different profiles, is surprisingly difficult to write well for larger data structures, and as often as not is rejected primarily because it fails to conform to any of the profiles. Turtle has two profiles that have very clear syntax (Turtle and Turtle-Star), with Turtle-star being only slightly less clear because of a few edge cases that haven’t been fully resolved. Additionally, when people refer to Turtle, they are usually actually talking about TRIG, which extends the turtle language to incorporate named graphs (TRIG is backwards compatible with Turtle).
-   **Semantics Matter.** JSON requires local knowledge to be useful. Turtle does not, because there are in general enough core conventions in place (RDF, RDFS and perhaps minimal OWL) that meaning can be extracted very quickly through the application of known rules, even without deep contextual knowledge. Because Turtle is built around namespaces, those namespaces can also provide additional bootstrapped metadata to achieve semantic awareness in the data, while JSON requires manual intervention to provide a pale copy of this capability.
-   **Turtle represents complex structures better than JSON.** While the Turtle breakdown in the previous section shows a normalized structure, a Turtle parser could reconstruct a fully denormalized Javascript or Python object or JSON document in any number of ways, depending upon what kind of structure is desired. Both Python and Javascript have libraries for parsing Turtle as well (check out FrogCat’s ttl2jsonld at [https://github.com/frogcat/ttl2jsonld](https://github.com/frogcat/ttl2jsonld) for just one of many examples). It is this dual nature of RDF – as data documents and normalized data records – that makes RDF so compelling as services become more declarative and end up with less intervention on the part of programmers.

## References

- https://www.datasciencecentral.com/why-json-users-should-learn-turtle/
- https://www.datasciencecentral.com/why-graphql-will-rewrite-the-semantic-web/