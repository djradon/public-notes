---
id: s5z9wyb92268nr1b0cyl20n
title: "Let's Reboot the Semantic Web with Role-Playing"
desc: "I'd bet the Old Man in the Cave can help us out some."
updated: 1727297476325
created: 1726095395686
---

![](/assets/images/2024-09-13-16-11-46.png)

> "Friends, Romans, Farm Animals! We are now going up to the cave and check your favorite recluse. We're gonna bring him out in the sunshine and get a good look at him. And then we're gonna decide if he's worthwhile keeping alive." 
> 
> -Major French, The Twilight Zone: [[video.twilight-zone.s05e07-the-old-man-in-the-cave]]

## Learning In Public

Welcome to my developer journal. 

I'm on a mission to help people build, deconstruct, remix, and engage with the [[multiverse|t.multiverse]], primarily through [[computer-assisted role-play (CARP)|t.role-playing.computer-assisted]] and other [[interactive drama|t.drama.interactive]].

The vision is virtual realities (in the broadest sense) worthy of our engagement and an accompanying new artform that weaves together aspects of film, video games, role-playing games, and immersive theatre. I like to call it the [[idea.the-magic-store]], and in additional to imagination and artistry, it will require distributed, interoperable, and well-defined data. Which just happens to be the vision of the [[t.cs.semantic-web]].

So in addition to my main mission mapping out the technical and conceptual landscape of [[computer-assisted role-play|t.role-playing.computer-assisted]], I have a side-quest to reboot the Semantic Web. 

## Spoiler Alert: It's a Machine

In the eponymous Twilight Zone episode from 1959, the old man in the cave is secretly a computer that keeps the local townsfolk alive by giving them the information they need (through an intermediary, their leader Goldsmith) to survive in a radioactive, post-apocalyptic world. They end up destroying the computer in the name of freedom, and then everyone except Goldsmith dies of radiation poisoning. 

It's a story about secular faith and a nice example of the [[t.story-telling.tropes.benevolent-ai]] trope.

So in the context of this devlog, the Old Man is a metaphor for synthetic intelligence and how we can use digitized knowledge to help humanity.

## Making the Semantic Web Usable

The vision of the Semantic Web is simple: distributed, interoperable, and well-defined data.

The threads of the Semantic Web are [[prdct.rdf]] statements composed of a subject, a predicate, and an object. The form is beautiful in its simplicity. For example:

```turtle
:the-old-man-in-the-cave :helped :goldsmith .
:goldsmith :helped :the-townsfolk .
```

But of course, the devil is in the details. I guess we should've expected it to take a while to iron the kinks out of something as ambitious as a universal data language. Still, it's been almost 25 years!

I want to heed [[Manu Sporny|user.manu-sporny]]'s 2014 [[call-to-arms|ar.json-ld-and-why-i-hate-the-semantic-web]]: "If you want to make the Semantic Web a reality, stop making the case for it and spend your time doing something more useful, like actually making machines smarter or helping people publish data in a way that’s useful to them." 

Turns out that making machines smarter was the easy part!

With the current state of the art, publishing **any** semantic data is still hard, let alone useful data. In a word, the biggest issue for wider SW adoption is **usability**. 

I've got some ideas for how to make data publishing free and easy for everyone. So that should help usability.

To make published data useful, we'll need to address some big issues around RDF expressivity: [[temporality|t.cs.data.temporality]], [[provenance|t.km.meta-knowledge.provenance]], [[n-ary relationships|t.cs.semantic-web.n-ary-relationships]], hypotheticals, [[probabilities|t.cs.data.probability-claims]], and [[multi-level theory|t.km.ontology.multi-level-theory]].

Don't even get me started on the state of [[prdct.RDF-star]].

There are also plenty of gaps around SW infrastructure and best practices that have had me searching for solutions and dreaming up my own. I've got a glimmer of a solution to the [[httpRange-14 issue|vs.resources-that-refer-vs-resources-that-are#possible-solutions]], for example. Stay tuned next week!

In the trenches of academia, industry, and the World Wide Web Consortium, the Semantic Web has gotten bogged down. But hopefully we can forge a path forward. And I'd bet the old man in the cave can help us out some.

## Likely Topics

At the moment, I'm especially interested in role-playing *data modeling* and how to represent things like characters, stories, and evolving worlds. To that end, I'll be writing about [[applied ontology|t.km.ontology.applied]], [[linked data|t.cs.data.linked]], [[semantic methodologies|c.methodology.semantic-web]], virtual reality, and [[geographic information systems|t.cs.gis]]

In the near term, I'm hoping to develop some upper-level and meta-conceptualizations, i.e., ontologies, with related best practices, and weave together some publishing infrastructure.

I'm also interested in and wary of AI (better termed [[synthetic intelligence|t.cs.synthetic-intelligence]]) and how it can help people role-play and create [[interactive drama|t.drama.interactive]]. Things like [[t.cs.ai.retrieval-augmented-generation.graphrag]] and [[agentic systems|t.cs.agents]] are highly relevant.

I intend to touch on related topics in [[data science|t.cs.data.science]] and [[software development|t.cs.sd]] including [[software architecture|t.cs.sd.architecture]], [[visualization|t.cs.data.visualization]] and [[product design|t.pdm.design]]. 

## Next Steps

If you might be interested in the less-technical aspects of my mission, or [[story-telling|t.story-telling]] and the [[digital humanities|t.humanities.digital]] in general, check out my other blog, [Carpe Noctem]().

In any case, I'm looking to make connections that could lead to collaboration. If our interests overlap, please reach out!

Now, let's go pull the old man out of his cave and have a good look.


