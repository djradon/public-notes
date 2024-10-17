---
id: ebbj5ovrdqvao6v4mhxxb0o
title: Where‘s the Simple Semantic Web Authoring Tool?
desc: ''
updated: 1729157278177
created: 1729093723913
---

![](/assets/images/2024-10-08-10-10-13.png)

## Has it been two weeks already?

Actually, it‘s been closer to three weeks since my [first post](https://theoldmaninthecave.substack.com/p/lets-reboot-the-semantic-web-with-alternate-realities).

Why so long? Those ~900 words were so agonized that I‘m still recovering. I also wanted to get some work done that was worth writing about. I‘ve been going from minus one to zero for long enough already.

But I do want this dev journal to be somewhat regular even when productivity is slow. So I‘m going to lower my standards and just publicize some learnings, goddammit. Judging from my ChatGPT chat histories, there are more than enough learnings to choose from. I‘ll save the over-polishing for my other blog, [[blogs.carpe-noctem]].

So anyhow, I was raring to go on a revolutionary [[foundational ontology|t.km.ontology.foundational]] and accompanying example data, when...

## Let me just open the preferred Semantic Web authoring tool

I‘ve been composing little bits of raw RDF in [[Turtle|prdct.rdf.turtle]] “by hand” with my ~~preferred text editor~~ all-time-favorite software, [[VSCode|prdct.vscode]]. Turtle is the most human-readable of the various RDF syntaxes and with the nice [[Stardog RDF extension|prdct.stardog.rdf-grammars]] for syntax checking and highlighting the experience is pretty good. I wouldn‘t recommend it for non-coders though.

I‘ve been using the hallowed and venerable [[Protege application|prdct.protege]] “ontology editor” to browse raw ontology files. I know it has some support for instance data, but it doesn‘t have “source editing”; it‘s complicated and intimidating; and it‘s not ideal for actual data management. Stick to the [[t-box|vs.tbox-vs-abox-vs-mbox]], Protege.

[[prdct.topbraid-composer]] is the other well-known GUI tool for the Semantic Web, but the free edition was discontinued in May 2020, and the paid “Maestro Edition” is $3450/year and no longer actively developed. ([[org.topquadrant]] is focusing on [[prdct.topbraid-edg]] which has neither a free version nor public pricing.) 

So Composer Free Edition (download [here](https://archive.topquadrant.com/topbraid-composer-install/)) might be your best option for affordable, GUI-based RDF data management.

For me, not being able to see the source for more than one element at a time is disqualifying, but maybe I was just doing something wrong. Also, the old free edition didn‘t seem to work with [[prdct.rdf.trig]] (the “named graph” superset of Turtle), which might be a major issue for me. And like most products based on the [[Eclipse IDE|prdct.eclipse]], learning Composer might be a challenge for non-programmers.

So I started a frustrating search for friendlier [[authoring tools|c.software.semantic.authoring]]. Surely there‘s something that allows you to *browse, create, and update RDF data* with a GUI, like [[prdct.Excel]] or [[prdct.datagrip]] but for the Semantic Web!? 

A purpose-built application for a general audience should have:
  - simple ways of entering and updating data with consistency checks and, ideally, a revision history or undo mechanism
  - graph and hierarchy visualization
  - wizards and other user-experience affordances for common workflows like setting up projects, commiting changes, and managing and publishing datasets

Ideally, I‘d want a stand-alone application that you can run disconnected on a laptop. 


## What Are the Other Options?

The only stand-alone alternative to Protege and TopBraid Composer that I could find was [[prdct.fluent-editor]]. It‘s quirky, doesn‘t have direct source editing, and hasn‘t been updated since 2015. I love the idea of using Controlled English for modeling knowledge, but LLMs are poised to do that in any language, controlled or not. 

Fluent Editor was definitely ahead of its time.

## Reddit To the Rescue?

While researching this post, I stumbled on a recent [[reddit entitled “Best Ontology Development Environment Tool?”|ar.reddit.semanticweb.best_ontology_development_environment_tool]]. 

It mentioned [[prdct.atomicserver]]/[[prdct.atomic-data]], which is an exciting RDF-based alternative to the conventional semantic web. I particularly love its use of [[t.cs.sd.event-sourcing]].

According to creator [[user.joep-meindertsma]], it “now has an ontology editor with a nice UI, even shows the UML diagram.” Sounds great, but...

I have some [[hesitations about the Atomic approach|prdct.atomic-data#thoughts]], especially in view of my [[alternate realities use case|blogs.the-old-man-in-the-cave.2024-09-27-lets-reboot-the-semantic-web-with-alternate-realities]]. Primarily, it is too restrictive about being able to say anything about anything, and all data requires validation with an Atomic Schema before it‘s stored on an Atomic-compatible service. I want something flexible where data can be stored in Git repositories and get forked easily.

Still, I admire the ambition, love the [strategy](https://docs.atomicdata.dev/roadmap), and depending on your use case, it might work for you.

The Reddit thread mentioned a few other web-based possibilities:

- [[prdct.linkeddatahub]] is an incredible, web-based, open-source Knowledge Graph platform that deserves an article of its own. Its target audience includes “researchers and data scientists” and “developers and data publishers.“ While it could be used for authoring RDF data, it seems like overkill as an authoring tool.
- [[prdct.metaphactory]] is similar, but not open-source
- [[prdct.stardog.studio]] looks slick and might fit the bill if it worked with text files or non-Stardog triple stores.
- [[prdct.semaphore]] the most overkill anywhere!

The consensus in the Reddit discussion seemed to be: if you‘re comfortable using an IDE, making RDF data by hand is probably your best option.

### Solid?

At this point, I should probably mention [[prdct.solid]], a specification and platform that lets people store their data securely in decentralized data stores called Pods. It‘s similar to Atomic Data and also exciting and ambitious, with a large and active community to boot. But while Solid is based on RDF, it‘s not viable as a general RDF authoring tool. It could benefit from one though!

### Anything Else?

[[prdct.vocbench]] might be the best web-based alternative. You can install it locally and it seems to have decent support for mixing local development with connected resources. But it doesn‘t seem to have a source editor and it has some [[other limitations|pub.question-log.2024.10.16#limitations-of-vocbench]].

There‘s also the [[prdct.open-link-structured-data-editor-osde]], which hasn‘t seen an update in two years and doesn‘t work with text files. 

### Conclusion

The situation is disheartening to say the least.

If we‘re going to reboot the semantic web, we‘re going to need a tool that supports local-first authoring that can provide guided workflows and data guardrails.

For now, I guess I‘ll be sticking with VSCode, but please let me know if I missed something.