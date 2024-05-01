---
id: l8mxuujoo2p7ydvttea8v4n
title: >-
  Assessment and Benchmarking of Spatially Enabled Rdf Stores for the Next
  Generation of Spatial Data Infrastructure
desc: ''
updated: 1714508988026
created: 1714498601292
---

- https://www.mdpi.com/2220-9964/8/7/310

## Abstract

Geospatial information is indispensable for various real-world applications and is thus a prominent part of today’s data science landscape. Geospatial data is primarily maintained and disseminated through spatial data infrastructures (SDIs). However, current SDIs are facing challenges in terms of data integration and semantic heterogeneity because of their partially siloed data organization. In this context, linked data provides a promising means to unravel these challenges, and it is seen as one of the key factors moving SDIs toward the next generation. In this study, we investigate the technical environment of the support for geospatial linked data by assessing and benchmarking some popular and well-known spatially enabled RDF stores (RDF4J, GeoSPARQL-Jena, Virtuoso, Stardog, and GraphDB), with a focus on GeoSPARQL compliance and query performance. The tests were performed in two different scenarios. In the first scenario, geospatial data forms a part of a large-scale data infrastructure and is integrated with other types of data. In this scenario, we used ICOS Carbon Portal’s metadata—a real-world Earth Science linked data infrastructure. In the second scenario, we benchmarked the RDF stores in a dedicated SDI environment that contains purely geospatial data, and we used geospatial datasets with both crowd-sourced and authoritative data (the same test data used in a previous benchmark study, the Geographica benchmark). The assessment and benchmarking results demonstrate that the GeoSPARQL compliance of the RDF stores has encouragingly advanced in the last several years. The query performances are generally acceptable, and spatial indexing is imperative when handling a large number of geospatial objects. Nevertheless, query correctness remains a challenge for cross-database interoperability. In conclusion, the results indicate that the spatial capacity of the RDF stores has become increasingly mature, which could benefit the development of future SDIs.