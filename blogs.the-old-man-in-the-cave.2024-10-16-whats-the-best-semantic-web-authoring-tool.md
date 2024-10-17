---
id: ebbj5ovrdqvao6v4mhxxb0o
title: What‘s the Best Semantic Web Authoring Tool?
desc: a grim survey of RDF data management apps
updated: 1729194501054
created: 1729093723913
---

![](/assets/images/2024-10-08-10-10-13.png)

## Has it been two weeks already?

Actually, it‘s been closer to three weeks since my [first post](https://theoldmaninthecave.substack.com/p/lets-reboot-the-semantic-web-with-alternate-realities).

Why so long? Those ~900 words were so agonized that I‘m still recovering. Also wanted to get some work worth writing about done. I‘ve been going from minus one to zero for long enough already.

But this dev journal should be somewhat regular even when output is slow. So I‘m going to lower my standards and just publicize some learnings, goddammit. Judging from my ChatGPT chat histories, there are more than enough learnings to choose from. I‘ll save the over-polishing for my other blog, [[blogs.carpe-noctem]].

So anyhow, I've been raring to go on a revolutionary [[foundational ontology|t.km.ontology.foundational]] and accompanying example data. Let me just open my go-to Semantic Web authoring tool...

## The Usual Suspects 

I‘ve been composing little bits of raw RDF in [[Turtle|prdct.rdf.turtle]] “by hand” with my ~~preferred text editor~~ all-time-favorite software, [[VSCode|prdct.vscode]]. Turtle is the most human-readable of the various RDF syntaxes and with the handy [[Stardog RDF extension|prdct.stardog.rdf-grammars]] for syntax checking and highlighting, the experience is pretty good. I wouldn‘t recommend it for non-coders though, and even coders deserve something better.

For a little GUI goodness, I‘ve been using the hallowed and venerable [[Protege application|prdct.protege]] “ontology editor” to browse raw ontology files. I put ontology editor in quotes here because there's been an [[annoying blurring of the line|pub.question-log.2024.10.12#its-so-annoying-that-applications-and-the-semantic-web-community-seem-to-refer-to-instance-data-as-an-ontology]] between ontologies (i.e., conceptual schemas, also known as the “terminologic box“) and the facts and entities that use ontologies, aka instance data or the “assertional box.“

I know Protege is commonly used for instance data, probably because of its mature [[reasoner|c.software.reasoner]] support. But it doesn‘t have source editing; it‘s complicated and intimidating; and it‘s not ideal for actual data management. 

[[prdct.topbraid-composer]] is the other well-known GUI tool for the Semantic Web, but the free edition was discontinued in May 2020, and the paid “Maestro Edition” is $3450/year and no longer actively developed. [[org.topquadrant]] is focusing on [[prdct.topbraid-edg]] which has neither a free version nor public pricing.

For me, not being able to see the source for more than one element at a time is disqualifying, but maybe I was just doing something wrong. Also, the old free edition didn‘t seem to work with [[prdct.rdf.trig]] (the “named graph” superset of Turtle), which might be a major issue for me. And like most products based on the [[Eclipse IDE|prdct.eclipse]], learning Composer might be a challenge for non-programmers.

Even so, Composer Free might be your best option for affordable, GUI-based RDF data management. You can find the slightly-hidden download [here](https://archive.topquadrant.com/topbraid-composer-install/).


## A Frustrating Search

I started looking for a friendlier, purpose-built [[authoring tool|c.software.semantic.authoring]]. Surely there‘s something that allows you to *browse, create, and update RDF data* with a GUI!? Like [[prdct.Excel]] or [[prdct.datagrip]], but for the Semantic Web. I mean, people have been doing this for 25 years!

You would expect a user-friendly data management app to have a simple means of entering and updating data. Helpful graph and hierarchy visualizations would be nice. It should also have guardrails:
  - consistency checks
  - a revision history or per-object undo mechanism
  - wizards and other user-experience affordances for common workflows like setting up projects, commiting changes, and publishing datasets

Ideally, I‘d want a stand-alone application that you can run disconnected on a laptop. (Local-first forever!)

### There Must Be Plenty of Options, Right?

The only stand-alone alternative to Protege and Composer that I could find was [[prdct.fluent-editor]]. It‘s quirky, doesn‘t have direct source editing, and hasn‘t been updated since 2015. I love the idea of using Controlled English for modeling knowledge, but LLMs are poised to do that in any language, controlled or not. 

Fluent Editor was definitely ahead of its time, but I'd be suprised to hear of anyone using it in 2024.

## Reddit To the Rescue?

While researching this post, I stumbled on a recent [[reddit entitled “Best Ontology Development Environment Tool?”|ar.reddit.semanticweb.best_ontology_development_environment_tool]]. 

### Atomic 

It mentioned [[prdct.atomicserver]], which implements the [[prdct.atomic-data]] spec. Atomic Data is an exciting RDF-based alternative to the conventional semantic web. I particularly love its use of [[t.cs.sd.event-sourcing]].

According to creator [[user.joep-meindertsma]], it “now has an ontology editor with a nice UI, even shows the UML diagram.” Sounds great, but...

I have some [[hesitations about the Atomic approach|prdct.atomic-data#thoughts]], especially in view of my [[democratized alternate realities use case|blogs.the-old-man-in-the-cave.2024-09-27-lets-reboot-the-semantic-web-with-alternate-realities]]. Primarily, it is too restrictive about being able to say anything about anything, and all data requires validation with an Atomic Schema before it‘s stored on an Atomic-compatible service. I want something flexible where data can be stored in Git repositories and get forked easily.

Still, I admire the ambition, love the [strategy](https://docs.atomicdata.dev/roadmap), and depending on your use case, it might work for you.


### Overkill Options

The Reddit thread mentioned a few other web-based possibilities: LinkedDataHub, Metaphactory, Stardog Studio, and Semaphore.

[[prdct.linkeddatahub]] is an impressive, web-based, open-source Knowledge Graph platform that deserves an article of its own. Its target audience includes “researchers and data scientists” and “developers and data publishers.“ It inspires you, as a developer, to base your application on it.But, while it could be used for authoring RDF data, it seems like overkill as an authoring tool.

[[prdct.metaphactory]] is similar, but not open-source. And pricing isn't cheap, [“starting from $13.03/hr or from $52,900.00/yr” on Amazon](https://aws.amazon.com/marketplace/seller-profile?id=a04eaa90-2616-469a-a304-96d35bd77641).

[[prdct.semaphore]] looks to be the most overkill of all!

[[prdct.stardog.studio]] looks slick and might fit the bill for an authoring tool if it worked with text files or non-Stardog triple stores.

The consensus in the Reddit discussion seemed to be: if you‘re comfortable using an IDE, making RDF data by hand is probably your best option.

## Anything Else?

[[prdct.vocbench]] might be the best web-based alternative. You can install it locally and it seems to have caching and decent support for mixing local development with connected resources. It has options for history, validation, and undo. But it doesn‘t seem to have a source editor and it has some [[other limitations|pub.question-log.2024.10.16#limitations-of-vocbench]].

There‘s also the [[prdct.open-link-structured-data-editor-osde]], which hasn‘t seen an update in two years and doesn‘t work with text files. Catchy name, tho.

Finally, there's [[prdct.rdf4j.workbench]]. You can enter RDF directly into an HTML &lt;textarea&rt;. 

![](/assets/images/2024-10-17-12-06-02.png)

A picture is worth a lot of words here, but I‘ll spend some anyhow: If your text-oriented application has to be web-based, it has to use [[prdct.monaco-editor]].

### Solid?

At this point, I should probably mention [[prdct.solid]], an initiative/specification that lets people store their data securely in decentralized data stores called Pods. The vision is data is decoupled from applications, so that people are no longer locked into specific platforms simply because their data is held there. 

It‘s similar to Atomic Data and also exciting and ambitious, with a large and active developer community and commercial backing to boot. But while Solid is built on RDF, it‘s not viable as a general RDF authoring tool. 

It could benefit from one though.


## Prognosis

The situation is disappointing to say the least.

If we‘re going to [[reboot the semantic web|blogs.the-old-man-in-the-cave.2024-09-27-lets-reboot-the-semantic-web-with-alternate-realities]], we‘ll want a usable data editor that supports [[t.cs.sd.local-first]] authoring, guided workflows and data guardrails.

For now, I guess I‘ll be sticking with VSCode, but let me know if I‘ve missed something. I‘d love to be wrong here. 

Also, let me know if you're interested in buildinng or backing a [[modern RDF data editor|wanted.modern-rdf-data-editor]]! That‘s a project I could sink my teeth into.