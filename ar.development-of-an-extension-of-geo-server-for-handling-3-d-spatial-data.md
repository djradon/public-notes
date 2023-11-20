---
id: 03prptw7a8zmx9clcm7nv5g
title: Development of an Extension of Geo Server for Handling 3 D Spatial Data
desc: ''
updated: 1700507830720
created: 1700507492346
---

- url: https://scholarworks.umass.edu/cgi/viewcontent.cgi?article=1004&context=foss4g

## Highlights

- 2. Related Work
There are several DBMSs that can store 3D spatial data and perform query processing on spatial information. Oracle Spatial and Graph, a representative commercial database, supports most spatial operations and 3D spatial data types, including a solid geometry. PostGIS, a widely used open source spatial database, partially supports 3D spatial data types and operations. Although spatial DBMSs are fundamental to manipulate spatial data, common interfaces and tools have been demanded to satisfy various geospatial applications. For instance, users may need to overlay and manipulate multiple layers from various data sources without concerns about different implementations on each data store. GeoTools (GeoTools 1998) is an open source library that meets these requirements. It provides excellent abstraction for multiple data sources. GeoServer is an implementation of a geospatial data server based on GeoTools. It allows users to simply load/store layers from/to various databases and file-based data sources, hiding details of how to handle them. A read- able/writable source is called a data store. Thanks to many contributors, GeoServer supports a variety of data stores. Also, it lets users to add data stores via the Web. The reason is that GeoServer has a common interface, called Feature, between data stores and a module that provides the Web Feature Service. Thus, it acts as a bridge between heterogeneous data stores and the user interface, to exchange the spatial information.