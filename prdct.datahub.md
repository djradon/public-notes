---
id: gvkx03wwwnwaf47l4l0er2k
title: Datahub
desc: 'open-source metadata platform'
updated: 1709316859073
created: 1709281030821
---

- [[c.software.data-discovery]]
- repo: https://github.com/datahub-project/datahub

## Features

- You may be familiar with this [popular blog post](https://engineering.linkedin.com/distributed-systems/log-what-every-software-engineer-should-know-about-real-time-datas-unifying) on why logs should be at the heart of your data ecosystem. Turns out, the same is actually true about metadata as well. A modern data catalog  should enable real-time subscription to changes in the metadata as a first-class offering. 
- graph!

## References

- https://www.linkedin.com/blog/engineering/data-management/datahub-popular-metadata-architectures-explained
  - "Out of all the systems out there that we’ve surveyed, the only ones that have a third-generation metadata architecture are [[prdct.atlas]], [[prdct.egeria]], [[prdct.databook]], and [[prdct.datahub]]. Among these, Apache Atlas is tightly coupled with the Hadoop ecosystem. Some companies are experimenting with attaching Amundsen on top of Atlas to try to get the best of both worlds, but it seems like there are several challenges with this integration. For example, you must ingest your metadata and store it in Atlas’s graph and search index, bypassing Amundsen’s data ingestion, storage, and indexing modules completely. This means any new concepts you want to model need to be introduced as Atlas concepts, and then bridged with Amundsen’s UI, leading to quite a bit of complexity. Egeria supports an integration of different catalogs through a metadata event bus, but it doesn’t seem to be feature complete yet as of this writing. Uber Databook seems to be based on very similar design principles as DataHub, but is not available as open source. Of course, we are biased due to our personal experience with DataHub, but the open-sourced DataHub offers all the benefits of a third-generation metadata system with the ability to support multiple types of entities and relationships and a stream-first architecture."