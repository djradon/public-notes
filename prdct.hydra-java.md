---
id: wo0j6b7c6awk2gj48r22tcl
title: hydra-java
desc: ''
updated: 1701575073133
created: 1701574575382
url: https://github.com/dschulten/hydra-java/
---

## The Problem


The meaning of json attributes in api responses, their possible values etc. is usually not obvious without referring to some information coming from outside the resource itself. That is due to the nature of json. Two solutions immediately come to mind. Both are ways of vendor-specific documentation, some are machine-readable, some aren’t.

Describe the type in some sort of json-schema, wadl, raml, swagger or similar and publish it together with the resource. People could even generate classes from this information, if they wish to. My api users coming from a wsdl background scream for something like that.

Or put up documentation pages to describe your ex:doodad extension relation types and make the documentation available by dereferencing http://example.com/api/rels#doodad.

But one of the rules for a ReSTful API is:

> A REST API should never have “typed” resources that are significant to the client. Specification authors may use resource types for describing server implementation behind the interface, but those types must be irrelevant and invisible to the client. The only types that are significant to a client are the current representation’s media type and standardized relation names. \[Failure here implies that clients are assuming a resource structure due to out-of band information, such as a domain-specific standard, which is the data-oriented equivalent to RPC’s functional coupling\].

— Roy Fielding

My interpretation of this famous [rant by Roy Fielding](http://roy.gbiv.com/untangled/2008/rest-apis-must-be-hypertext-driven):

A publicly available media-type should give clients all necessary means to interpret a server response, and relation names for hyperlinks in the response must be recognizable based on public conventions, so that the client can act upon the responses it receives without knowing the details of a vendor-specific api.

In other words: If a client is told to make a reservation for a concert ticket, it should be able to recognize what one-fancy-api requires to achieve that without processing a vendor-specific documentation. How can we do that, purely based on a media type and relation names? Do we need hundreds of iana registered media types for all kinds of purposes?

## Solution (evolving)

I see [json-ld](http://www.w3.org/TR/json-ld/) (media type application/ld+json) as a possible way to solve this problem without forcing people to ask me about my vendor-specific documentation, thus decoupling the clients from my server types.

Clients should be able to understand a response based on widely available, standardized, public information.

The json-ld mediatype allows to bring descriptions of things in the real world from public vocabularies into your json files. With json-ld there **is** a way to say that a json response describes a [MusicEvent](http://schema.org/MusicEvent) which [offers](http://schema.org/offers) a [Ticket](http://schema.org/Ticket) without any vendor-specific documentation, and it can also link to other resources.

A popular vocabulary which describes things on the internet is [http://schema.org](http://schema.org). It is used by all major search engines for search engine optimization and sufficient for basic needs. It also integrates with other vocabularies, e.g. by using [additionalType](http://schema.org/additionalType) to point to [GoodRelations](http://purl.org/goodrelations/) classes or by using external enumerated values as shown by [DeliveryMethod](http://schema.org/DeliveryMethod).

(For those of you about to say that the Semantic Web never took off, please note that json-ld is [not about the Semantic Web at all](http://manu.sporny.org/2014/json-ld-origins-2/)).

[Hydra](http://www.hydra-cg.com/) adds interaction to the mix. It describes exactly how to post a ticket reservation.

So I want to add json-ld information to json objects serialized from my Java beans.

Java beans have no knowledge about the meaning of their bean properties and they do not know what they represent in the real world.

In the simplest possible case I want to design my json objects so that they can be understood by others based on schema.org. By simply calling my json transfer class `Person` and letting it have an attribute `name`, I want to get a publicly understandable json object

## Resources

- https://www.w3.org/community/hydra/wiki/Restbucks_with_Hydra #cool