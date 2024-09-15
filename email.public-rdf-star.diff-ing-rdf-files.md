---
id: l9zfd2id1vv4gc9yodetuog
title: Diff Ing Rdf Files
desc: ''
updated: 1726352245599
created: 1726330830400
---

- mentions: [[prdct.ontology-publisher]]


## Elissa Kendall




-------- Forwarded Message --------
Subject: 	Re: Diff'ing RDF files
Resent-Date: 	Sat, 14 Sep 2024 20:31:36 +0000
Resent-From: 	public-rdf-star-wg@w3.org
Date: 	Sat, 14 Sep 2024 20:31:25 +0000
From: 	Elisa Kendall <ekendall@thematix.com>
To: 	public-rdf-star-wg@w3.org <public-rdf-star-wg@w3.org>
CC: 	semantic-web@w3.org <semantic-web@w3.org>


Hi all,

 

There is an open-source tool available from the EDM Council for converting between RDF/XML, Turtle, and JSON-LD and for consistent serialization of any of these representations of RDF and OWL. The GitHub site for it is https://github.com/edmcouncil/rdf-toolkit. It is actively maintained, freely available, and addresses a number of issues mentioned on the thread, among other things. It also allows users to turn any of its features on/off as desired. It runs on the command line, or can be invoked automatically through GitHub commit hooks, for example.

 

For collaborative work across development teams for large ontology projects, consistent serialization for comparison purposes was one of our first and relatively important issues. It enables visual comparison in GitHub (and likely other source code management systems), so that anyone reviewing the changes can see exactly what changed, down to the single character level. There is also an axiomatic diff tool available via the OBO Foundry that folks might find useful, available at https://robot.obolibrary.org/.  I don’t know how well it works on RDF alone, mainly because I haven’t attempted to use it for that, but it works well as a companion tool to the RDF Toolkit from the EDM Council as needed.

 

We also have a pipeline that looks for a myriad of issues in ontologies, performs regression testing using examples and reference data, and includes an html-based publication process that itself has a comparison feature, enabling comparison of any pull request or prior release with another version or with the latest version. The code for this is also open source, available from the EDM Council GitHub repository, though support is required for hosting and customization.

 

Best regards,

 

Elisa

 

 

 
## Thomas Pellissier-Tanon

On 9/13/2024 11:50 PM, thomas@pellissier-tanon.fr wrote:
>> This is due to the fact that even a small difference can cause the 
> canonicalization to relabel blank node in a completely different way. So even blank nodes that were not impacted by the change may end up with different names, and so the text diff applied to the canonical form will report those as changes.
>
> A way to circumvent this issue is to tweak the "Issue Identifier Algorithm" part of RDF canonicalization to assign an identifier based on the node hash instead of a global counter. This way only blank nodes that have a path with only blank nodes vertices to the changed triples will get their ids changed and the other ones will stay the same.
>
> Thomas
>
>
> Le vendredi 13 septembre 2024 à 20:10, Florian Kleedorfer <florian.kleedorfer@austria.fm> a écrit :
>
>>
>>
>> Hi,
>>
>> Curious this is coming up just as an effort to get consistent formatting
>> for RDF (TTL for now) out the door on behalf of QUDT.
>>
>> Looked into canonicalization but the downside you mention is a
>> non-starter if you want to track changes with a version control system,
>> so we're just reproducing the input order of blank nodes by hacking into
>> the jena TTL parser.
>>
>> code: https://github.com/atextor/turtle-formatter
>>
>> which is being plugged into
>>
>> https://github.com/diffplug/spotless/ (maven plugin for now)
>>
>> Bottom line: you'll be able to format TTL consistently with the spotless
>> maven plugin soonish. Maybe one day, you won't even lose your comments.
>>
>> Reach out if you want to help making it work for other formats or if you
>> want a gradle/sbt plugin
>>
>> Best regards,
>> Florian
>>
>> Am 2024-09-13 16:18, schrieb Pierre-Antoine Champin:
>>
>>> Dear all,
>>>
>>> yesterday during the RDF-star working group call, I mentioned that RDF
>>> canonicalization [1] can be used to build a crude RDF "diff" tool, and
>>> that I was using a small script that I wrote for that. Other
>>> participants expressed interest for this script, so I cleaned it up a
>>> bit and published it here:
>>>
>>> https://gist.github.com/pchampin/7017fa5ff607e5bedf65e2f9954cfd46
>>>
>>> As indicated at the top, it relies on my Sophia library [2] for parsing
>>> and canonicalizing, but it can be easily adapted to use other
>>> command-line tools (for a while, I was using Gregg Kellogg's Ruby
>>> implementation [3]).
>>>
>>> Note that I describe it as a crude tool because
>>>
>>> - if the two graphs/dataset are isomorphic (i.e. identical modulo blank
>>> node labels), it will show no difference,
>>> - BUT if there is only the slightest difference, the tool may report a
>>> lot of changes, not all of them relevant.
>>>
>>> This is due to the fact that even a small difference can cause the
>>> canonicalization to relabel blank node in a completely different way.
>>> So even blank nodes that were not impacted by the change may end up
>>> with different names, and so the text diff applied to the canonical
>>> form will report those as changes.
>>>
>>> But despite these "false positives", I find it quite useful, and you
>>> might too. In particular, if the changes only impact triples/quads on
>>> IRIs and literals, the diff will be "exact".
>>>
>>> best
>>>
>>> [1] https://github.com/w3c/rdf-canon
>>> [2] https://github.com/pchampin/sophia_rs
>>> [3] https://ruby-rdf.github.io/
>
