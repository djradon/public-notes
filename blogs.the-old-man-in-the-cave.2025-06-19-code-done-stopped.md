---
id: bhklm07q12a6ir1rw4pnd3w
title: 2025 06 19 Code Done Stopped
desc: ''
updated: 1750445507888
created: 1750387410608
---

My last post had something dramatically wrong. And the path to the light has been tortuous. 

By the time I'd proudly reported [Semantic Flow](https://github.com/semantic-flow/sf-cli) code to be flowing, I'd already made a last, pathetic commit:

![](/assets/images/2025-06-19-20-17-32.png)


But I'm happy to say that, eight annoying months later, things might be back on track. No code yet, but I think I've got a pretty polished blueprint for a data revolution. I like to think of it as the [[idea.mr-fusion]] of the semantic web.

![](/assets/images/2025-06-19-20-31-31.png)

Also, I've been refining my vibe-coding on a glorified file copier called [[proj.weave]], and can confidently say that nothing gets the ol’ code flowing faster than connecting your IDE to those miraculous LLMs everyone's talking about. [[Cline|prdct.cline]] is my conduit of choice and it's amazing too. I'll detail how I'm using Dendron to give Cline memory in a future post.

## Corrections

In the world of data, an entity is a real or imaginary thing —- physical, digital, conceptual, or otherwise. 

In my last post, I wrote that “The central conceit of Semantic Flow is that every entity worth its salt should be associated with at least two sets of versioned datasets: a catalog series and a default series.” It should've been something more like “All an entity really needs is a good identifier.” Although I think a good catalog helps too.

I was assuming that an identifier should be co-located with at least some data that uses it. You see this on ontology websites all the time: the IRIs used to identify ontology terms, when copied into a browser address bar, return semantic data about that thing. (see also [[proj.tomitc.drafts.solving-httprange-14]])

Another, smaller note: I should've used “intelligible” instead of “legible” when I was talking about what we should expect for an identifiable thing from its namespace and name. To me intelligibility implies legibility, i.e., the ability for humans to read it easily. But and identifier should also provide the ability to conecptualize a thing. 

## Where I Got Stuck

Any hosted repository should have a corresponding website, and gitlab and github proved free websites via their similar "pages" features. 

I wanted to find a [[c.software.web.static-site-generator-ssg]] that I could extend for generating the websites that will support the semantic web revolution. And I wanted to use it to build websites for my code repos. 

There are lots of SSGs out there, but [[prdct.lume]] hits my sweet spot of a) built on Deno, b) extensible, and c) not too complicated to understand. It's elegant and brilliant and inspiring.

So I sidetracked into making (or more accurately, ripping off) a beautiful Lume theme, and I made a really bad decision about how to do it that led me to start building [[proj.weave]], which was a great learning experience, but not (it turns out) strictly necessary for just creating repo documentation sites.

And that thing clogged up too. And then my house burned down, after which I started doing a lot of pleasure reading. (Historical fiction lovers, I heartily recommend the [[superwork.house-of-nicollò]] series if you need some serious procrastination). 

## How I Got Unstuck

I got a sweet gig working on [[utility rate plan data|t.energy.rate-plan-data]], with real potential to help people and the planet. If we can help customers, government, industry, and advocacy groups to publish, discover and leverage energy data, we could optimize our usage, encourage competition, and hopefully accelerate the green energy transition.

So I'm back on the semantic data publishing bandwagon. Here's hoping I can ride this sucker to the moon.

## What I Got Right

> Grouping dataset versions into a series is the heart of Semantic Flow

Yes! Well, one heart is good identifiers, i.e. IRIs that:

1. are intelligible
2. are easy to mint
3. persist, cheaply

The other heart, versioned (semantic) datasets, should:

1. be explorable and accessible
2. be easy to create and evolve
4. persist, cheaply

The [[Semantic Flow IRI scheme|sflow.concepts.iri]] should take care of IRI intelligibility. [[sflow.concepts.catalog]] should take care of explorability and accessibility. Github and Gitlab are great at cheap persistence. 

[[sflow]] will handle the rest.  

## Where I'm Going

Lume, with perhaps some custom templates and plugins, can handle turning a Semantic Flow source folder into a website.

