---
id: ebbj5ovrdqvao6v4mhxxb0o
title: Where‘s the Semantic Web Tooling?
desc: ''
updated: 1729121686684
created: 1729093723913
---

## Has it been two weeks already?

Actually, it's been closer to three weeks since my [first post](https://theoldmaninthecave.substack.com/p/lets-reboot-the-semantic-web-with-alternate-realities).

Why so long? Those ~900 words were so agonized that I'm still recovering. I also wanted to get some work done that was worth writing about. I've been going from minus one to zero for long enough already.

But I do want this dev journal to be somewhat-regular even when progress is slow. So I'm going to lower my standards and just publicize some learnings, goddammit. There are more than enough to choose from. I'll save the over-polishing for [[blogs.carpe-noctem]].

So anyhow, I was raring to go on a revolutionary [[foundational ontology|t.km.ontology.foundational]]  and then...


## Let Me Just Open the Preferred Semantic Web GUI...

What tool do people use to create and manage semantic data? 

I've been composing little bits of RDF in my ~~favorite text editor~~ all-time-favorite tool, [[vscode|prdct.vscode]] and enjoying the awesome [[prdct.stardog.rdf-grammars]] for syntax checking and highlighting.

But surely there's something that allows you to *browse, create, and update data* with a GUI, like [[prdct.datagrip]] but for RDF!?

I've been using the hallowed and venerable [[prdct.protege]] to browse raw ontology files. I know it has some support for instance data, but it doesn't have "source editing" and it does seem oriented towards the [[tbox|vs.tbox-vs-abox]].

[[prdct.topbraid-composer]] is the other well-known tool, but the free edition was discontinued in May, 2020. The paid “Maestro Edition” is $3450/year and no longer actively developed. [[org.topquadrant]] is focusing on [[prdct.topbraid-edg]] which has neither a free version nor public pricing.

So I started a frustrating search for better [[authoring tools|c.software.semantic.authoring]].

[[prdct.vocbench]] might be the best lesser-known alternative. It's a web app, but you can install it locally and it seems to have decent support for mixing local development with connected resources. But it doesn't seem to have a text editor and it has some [[other limitations|pub.question-log.2024.10.16#limitations-of-vocbench]].

[[prdct.fluent-editor]] was an eye-opener, but doesn't have direct source editing and hasn't been updated since 2015. It uses Controlled English as a knowledge modeling language, something LLMs are poised to take over. Definitely ahead of its time.

There's also the [[prdct.open-link-structured-data-editor-osde]], which hasn't seen an update in two years and requires an RDF service.

Turns out there was a [[reddit titled “Best Ontology Development Environment Tool?”|ar.reddit.semanticweb.best_ontology_development_environment_tool]] started a couple weeks ago, right around the time I started my search. They mostly came to the same conclusion: if you're comfortable using an IDE, making RDF data by hand is probably the best option. The alternatives are few, clumsy and mostly moribund.

That thread did mention [[prdct.atomicserver]], which is an  exciting RDF-based alternative to the conventional semantic web. I have some [[concerns about the approach|prdct.atomic-data#thoughts]]. Primarily, it is more restrictive about being able to say anything about anything. But I admire the ambition and love the [strategy](https://docs.atomicdata.dev/roadmap). 


If we're going to revolutionize the semantic web, we're going to need a tool that supports local-first hacking on semantic data in text files, but ideally with something graphical to provide people with a visualizations, guided workflow, and guardrails.

![](/assets/images/2024-10-08-10-10-13.png)
