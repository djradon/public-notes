---
id: l8jZApjTwypJDlSzk2qJ1
title: HATEOAS
desc: Hypermedia as the Engine of Application State
updated: 1727999377415
created: 1636171046830
---

- related: [[prdct.hal]] [[prdct.json.hyper-schema]]


- [[c.Resource.List]] https://restfulapi.net/hateoas/
    - [[p.hasComment]] 

    - > The dynamic example would be when client building the menu based on links returned for the resource. So server (base on user’s authorization) will return only links accessible for the user and client will build the menu dynamically.
    - > clients needs to know about possible actions, but with hypermedia links they don’t have to know about the business logic. Say you have your typical blog with post resources. Some possible actions might be to like, edit, delete and archive posts. Without links, clients would need to know the business logic about when it is possible to like/edit/delete/archive a certain post resource. With links, the server tells clients what they can do, by providing the corresponding links.

- [[p.hasCriticism]]
  - https://medium.com/@andreasreiser94/why-hateoas-is-useless-and-what-that-means-for-rest-a65194471bc8
    - summary: no good server-side frameworks/tools and no good  clients

## Ideas

- could RDFa be used for embedding semantic data? 
  - Apparently
    - "When representations are provided in hypertext form with typed relations (using microformats of HTML, RDF in N3 or XML, or even SVG), then automated agents can traverse these applications almost as well as any human. There are plenty of examples in the linked data communities. More important to me is that the same design reflects good human-Web design, and thus we can design the protocols to support both machine and human-driven applications by following the same architectural style." [^1]


## Implementations

- [[prdct.spring.hateoas]]
- 


## Resources

- https://www.kapresoft.com/software/2023/11/09/rest-hateoas-best-practices.html
- https://www.baeldung.com/spring-hateoas-tutorial mentions [[prdct.spring.hateoas]]
- https://news.ycombinator.com/item?id=36944686
- https://unitcoding.com/implementing-hateoas/ mentions [[prdct.riskfirst_hateoas]]
- https://spring.io/guides/gs/rest-hateoas

## References

- https://softwareengineering.stackexchange.com/questions/388325/advantages-of-hateoas-based-restful-service

[^1]: - https://webofdata.wordpress.com/2009/12/15/hateos-revisited-rdfa/