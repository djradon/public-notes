---
id: cSy6NuQVsGugCWeDHyNK0
title: Atomspace
desc: in-RAM knowledge representation database
updated: 1696269809567
created: 1645899689960
---

- repo: https://github.com/opencog/atomspace
- written-in: #c++
- [[p.builtOn]] [[prdct.postgres]]
- [[p.hasRelatedTopic]] [[t.km.kr]] 
- "AtomSpace is a platform for building Artificial General Intelligence (AGI) systems. It provides the central knowledge representation component for OpenCog. As such, it is a fairly mature component, on which a lot of other systems are built, and which depend on it for stable, correct operation in a day-to-day production environment."

## [[p.hasFeature]]

-   **Search queries are graphs.** (The API to the [pattern engine](https://wiki.opencog.org/w/Pattern_engine) is a graph.) That is, every query, every search is also a graph. That means one can store a collection of searches in the database, and access them later. This allows a graph rule engine to be built up.
-   **Inverted searches.** ([DualLink](https://wiki.opencog.org/w/DualLink).) Normally, a search is like "asking a question" and "getting an answer". For the inverted search, one "has an answer" and is looking for all "questions" for which its a solution. This is pattern recognition, as opposed to pattern search. All chatbots do this as a matter of course, to handle chat dialog. No chatbot can host arbitrary graph data, or search it. The AtomSpace can. This is because queries are also graphs, and not just data.
-   Both [**"meet" and "join"**](https://en.wikipedia.org/wiki/Join_and_meet) searches are possible: One can perform a "fill in the blanks" search (a meet, with [MeetLink](https://wiki.opencog.org/w/MeetLink)) and one can perform a "what contains this?" search (a join, with [JoinLink](https://wiki.opencog.org/w/JoinLink).)
-   **Graphs are executable.** Graph vertex types include "plus", "times", "greater than" and many other programming constructs. The resulting graphs encode ["abstract syntax trees"](https://en.wikipedia.org/wiki/Abstract_syntax_tree) and the resulting language is called [Atomese](https://wiki.opencog.org/w/Atomese). It resembles the [intermediate representation](https://en.wikipedia.org/wiki/Intermediate_representation) commonly found in compilers, except that, here, its explicitly exposed to the user as a storable, queriable, manipulable, executable graph.
-   **Graphs are typed** ([TypeNode](https://wiki.opencog.org/w/TypeNode) and [type constructors](https://wiki.opencog.org/w/Type_constructor).) Graph elements have types, and there are half a dozen type constructors, including types for graphs that are functions. This resembles programming systems that have type constructors, such as CaML or Haskell.
-   **Graphs specify flows** ([Values](https://wiki.opencog.org/w/Value) and [DynamicFormulaLink](https://wiki.opencog.org/w/DynamicFormulaLink).) Graph elements host dynamic, mutable key-value databases. That is, every graph element has an associated key-value database. Think of the graph is "pipes" or "plumbing"; the key-value data is the mutable, dynamically changing "water" that flows through those pipes.
-   **Unordered sets** ([UnorderedLink](https://wiki.opencog.org/w/UnorderedLink).) A graph vertex can be an unordered set (Think of a list of edges, but they are not in any fixed order.) When searching for a matching pattern, one must consider **all** permutations of the set. This is easy, if the search has only one unordered set. This is hard, if they are nested and inter-linked: it becomes a constraint-satisfaction problem. The AtomSpace pattern engine handles all of these cases correctly.
-   **Alternative sub-patterns** ([ChoiceLink](https://wiki.opencog.org/w/ChoiceLink).) A search query can include a menu of sub-patterns to be matched. Such sets of alternatives can be nested and composed arbitrarily. (*i.e.* they can contain variables, *etc.*)
-   **Globby matching** ([GlobNode](https://wiki.opencog.org/w/GlobNode).) One can match zero, one or more subgraphs with globs This is similar to the idea of globbing in a regex. Thus, a variable need not be grounded by only one subgraph: a variable can be grounded by an indeterminate range of subgraphs.
-   **Quotations** ([QuoteLink](https://wiki.opencog.org/w/QuoteLink).) Executable graphs can be quoted. This is similar to quotations in functional programming languages. In this case, it allows queries to search for other queries, without triggering the query that was searched for. Handy for rule-engines that use rules to find other rules.
-   **Negation as failure** ([AbsentLink](https://wiki.opencog.org/w/AbsentLink).) Reject matches to subgraphs having particular sub-patterns in them. That is, find all graphs of some shape, except those having these other sub-shapes.
-   **For-all predicate** ([AlwaysLink](https://wiki.opencog.org/w/AlwaysLink).) Require that all matches contain a particular subgraph or satisfy a particular predicate. For example: find all baskets that have only red balls in them. This requires not only finding the baskets, making sure they have balls in them, but also testing each and every ball in a basket to make sure they are **all** of the same color. 