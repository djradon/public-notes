---
id: l8jZApjTwypJDlSzk2qJ1
title: HATEOAS
desc: Hypermedia as the Engine of Application State
updated: 1706249087416
created: 1636171046830
---



- [[c.Resource.List]] https://restfulapi.net/hateoas/
    - [[p.hasComment]] 

    - > The dynamic example would be when client building the menu based on links returned for the resource. So server (base on user’s authorization) will return only links accessible for the user and client will build the menu dynamically.
    - > clients needs to know about possible actions, but with hypermedia links they don’t have to know about the business logic. Say you have your typical blog with post resources. Some possible actions might be to like, edit, delete and archive posts. Without links, clients would need to know the business logic about when it is possible to like/edit/delete/archive a certain post resource. With links, the server tells clients what they can do, by providing the corresponding links.

- [[p.hasCriticism]]
  - https://medium.com/@andreasreiser94/why-hateoas-is-useless-and-what-that-means-for-rest-a65194471bc8
    - summary: no good server-side frameworks/tools and no good  clients


- url: https://parceljs.org/

## Resources

- https://www.kapresoft.com/software/2023/11/09/rest-hateoas-best-practices.html
- https://www.baeldung.com/spring-hateoas-tutorial
- https://news.ycombinator.com/item?id=36944686