---
id: am79bm4kfdggpfputqz267n
title: Design Issues
desc: ''
updated: 1712690474970
created: 1712687532553
---

- https://www.w3.org/DesignIssues/

## Linked Data

- https://www.w3.org/DesignIssues/LinkedData.html

* Use URIs as names for things
* Use HTTP URIs so that people can look up those names
* When someone looks up a URI, provide useful information, using the standards (RDF*, SPARQL)
* Include links to other URIs. so that they can discover more things. (sic)

## Icing on the cake

- "It would certainly be interesting for someone to make a web interface for a version control system which is all icing on the original cake, where at any point you can strip off the ,stuff and get back to the original file live on the web site"
  - @tim-berners-lee
- "The [[prdct.memento]] protocol is a good example of a machine-readable icing on the cake. It adds HTTP headers to allow older versions of a web page to be found, allowing a momento-equipped browser to explore the timeline of a web page's histroy.'"

### Conclusion

- the "icing on the cake" pattern, in which all services around a live web page are available at URIs made by adding small strings to the same URI, has many nice properties. It is easy to use, and scales well as new facilities are added. Future systems, especially version control systems, but also access control systems, should be desigend with that in mind. Not only should one make the facilities available to a human user by adding (say) the comma by hand, but also make the facilities visible to software by adding a link of some sort.