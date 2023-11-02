---
id: tla50szfndrzw1fycstyuwh
title: The Web after Tomorrow
desc: ''
updated: 1696447804899
created: 1696447105422
---

- #url https://tonsky.me/blog/the-web-after-tomorrow/
- [[p.mentioned]] [[prdct.datomic]]

## Highlights

- The big data source on the top is all the data we have in the project. Before reaching the client, it must come through two filters. First one is a security filter. It filters out all the data user is not authorized to see, leaving out just personal, shared and public rows. The second filter leaves only the parts user is interested in. For UI it means parts which are required to render current page. Everything that passes these two filters should be pushed to the client instantly, in real time. It is, by definition, everything client needs to render a page. ^9f1qxkkh215s
- "Query is a recipe to get the data from the storage. To get real-time, we need these queries to work the other way around. Client still defines its needs via query. This query might be used for initial data fetch, just as usual. The same query will then be used to filter whole-DB changelog and decide what parts of it server should push to which client. Fetch is about trying to get the data given the query. Push is about finding the affected subscriptions given the changed data." ^sw5qa6c54na5