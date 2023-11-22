---
id: 94ztvzmwd72rzabd3q4ngf6
title: Landscape Lab
desc: 'An open kit for developing game-based participatory planning tools.'
updated: 1697476572131
created: 1696889060484
---

- [[c.software.virtual-reality]]
url: https://landscapelab.boku.ac.at/

## [[c.component]]

-   The geodata for the game board are pre-processed with [QGIS](https://www.qgis.org/de/site/). QGIS is also used to send the map as a video stream for the projection.
-   The object recognition of the game tokens is realised with [OpenCV](https://opencv.org/) and Python.
-   The 3D environment is displayed with the free game engine [Godot](https://godotengine.org/).
-   The geo data is stored in a [PostGIS database](https://postgis.net/) or a geopackage. Single files like shapefiles or GeoTIFFs can be loaded additionally.
-   [GDAL](https://gdal.org/) is used for data import, projections and conversions.
-   A separate C++ plugin provides an interface between GDAL and Godot.