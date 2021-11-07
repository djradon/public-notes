---
id: l8jZApjTwypJDlSzk2qJ1
title: HATEOS
desc: Hypermedia as the Engine of Application State
updated: 1636172403855
created: 1636171046830
---


- [[p.hasResourceList]] https://restfulapi.net/hateoas/
    - [[p.hasComment]] 

    - > The dynamic example would be when client building the menu based on links returned for the resource. So server (base on user’s authorization) will return only links accessible for the user and client will build the menu dynamically.
    - > clients needs to know about possible actions, but with hypermedia links they don’t have to know about the business logic. Say you have your typical blog with post resources. Some possible actions might be to like, edit, delete and archive posts. Without links, clients would need to know the business logic about when it is possible to like/edit/delete/archive a certain post resource. With links, the server tells clients what they can do, by providing the corresponding links.

- [[p.hasCriticism]]
  - https://medium.com/@andreasreiser94/why-hateoas-is-useless-and-what-that-means-for-rest-a65194471bc8
