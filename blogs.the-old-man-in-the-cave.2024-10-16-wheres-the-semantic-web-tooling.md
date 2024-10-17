---
id: ebbj5ovrdqvao6v4mhxxb0o
title: Where‘s the Semantic Web Tooling?
desc: ''
updated: 1729150950154
created: 1729093723913
---

## Has it been two weeks already?

Actually, it‘s been closer to three weeks since my [first post](https://theoldmaninthecave.substack.com/p/lets-reboot-the-semantic-web-with-alternate-realities).

Why so long? Those ~900 words were so agonized that I‘m still recovering. I also wanted to get some work done that was worth writing about. I‘ve been going from minus one to zero for long enough already.

But I do want this dev journal to be somewhat regular even when productivity is slow. So I‘m going to lower my standards and just publicize some learnings, goddammit. Judging from my ChatGPT chat histories, there are more than enough learnings to choose from. I‘ll save the over-polishing for my other blog, [[blogs.carpe-noctem]].

![](/assets/images/2024-10-08-10-10-13.png)


So anyhow, I was raring to go on a revolutionary [[foundational ontology|t.km.ontology.foundational]] and accompanying example data, when...

## Let me just open the preferred Semantic Web authoring tool

I‘ve been composing little bits of RDF “source code” in [[Turtle|prdct.rdf.turtle]] “by hand” with my all-time-favorite software, [[vscode|prdct.vscode]]. Turtle is the most human-readable of the various RDF syntaxes and with the awesome [[prdct.stardog.rdf-grammars]] for syntax checking and highlighting, the experience is pretty good. I wouldn‘t recommend it for non-coders though.

A purpose-built tool for a general audience should have:
  - ways of visualizing data graphs and hierarchies
  - simple ways of entering and updating data with consistency
  - wizards and other user-experience affordances for common workflows like setting up projects, commiting changes, and ,managing and publishing datasets

I‘ve been using the hallowed and venerable [[Protege application|prdct.protege]] “ontology editor” to browse raw ontology files. I know it has some support for instance data, but it doesn‘t have “source editing”; it‘s complicated and intimidating; and it's not ideal for actual data management. Stick to the [[t-box|vs.tbox-vs-abox-vs-mbox]], Protege.

[[prdct.topbraid-composer]] is the other well-known GUI tool for the Semantic Web, but the free edition was discontinued in May 2020, and the paid “Maestro Edition” is $3450/year and no longer actively developed. ([[org.topquadrant]] is focusing on [[prdct.topbraid-edg]] which has neither a free version nor public pricing.) 

So Composer Free Edition (download [here](https://archive.topquadrant.com/topbraid-composer-install/)) might be your best option for affordable, GUI-based RDF data management.

For me, not being able to see the source for more than one element at a time is disqualifying, but maybe I was just doing something wrong. Also, the old free edition didn‘t seem to work with [[prdct.rdf.trig]] (the “named graph” superset of Turtle), which might be a major issue for me. And like most products based on the [[Eclipse IDE|prdct.eclipse]], learning Composer might be a challenge for non-programmers.

So I started a frustrating search for friendlier [[authoring tools|c.software.semantic.authoring]]. Surely there‘s something that allows you to *browse, create, and update RDF data* with a GUI, like [[prdct.Excel]],  or [[prdct.datagrip]] but for the Semantic Web!?

[[prdct.vocbench]] might be the best lesser-known alternative. It‘s a web app, but you can install it locally and it seems to have decent support for mixing local development with connected resources. But it doesn‘t seem to have a source editor and it has some [[other limitations|pub.question-log.2024.10.16#limitations-of-vocbench]].

[[prdct.fluent-editor]] was an eye-opener, but doesn‘t have direct source editing and hasn‘t been updated since 2015. It uses Controlled English as a knowledge modeling language, something LLMs are poised to take over. Definitely ahead of its time.

There‘s also the [[prdct.open-link-structured-data-editor-osde]], which hasn‘t seen an update in two years and requires an RDF service. I want something that works with text files.

Turns out there was a [[reddit titled “Best Ontology Development Environment Tool?”|ar.reddit.semanticweb.best_ontology_development_environment_tool]] started a couple weeks ago, right around the time I started my search. They mostly came to the same conclusion: if you‘re comfortable using an IDE, making RDF data by hand is probably the best option. The alternatives are few, clumsy and mostly moribund.

That Reddit thread did mention [[prdct.atomicserver]], which is an exciting RDF-based alternative to the conventional semantic web. According to the creator,  I have some [[concerns about the approach|prdct.atomic-data#thoughts]]. Primarily, it is more restrictive about being able to say anything about anything, and all data must be validated by an Atomic Schema before it‘s stored on an Atomic-compatible server. I need something that can store data in Git repositories, but I admire the ambition, love the [strategy](https://docs.atomicdata.dev/roadmap), and will continue to keep an eye on the project.

At this point, I should probably mention [[prdct.solid]], a specification and platform that lets people store their data securely in decentralized data stores called Pods. It‘s similar to Atomic Data and also exciting, with a large and active community to boot. But while the platform is based on RDF, it‘s not viable as an general RDF authoring tool.

The situation is disheartening to say the least.

If we‘re going to revolutionize the semantic web, we‘re going to need a tool that supports local-first authoring and management of semantic data in text files, but ideally with something graphical to provide people with visualizations, guided workflows, and data guardrails.

