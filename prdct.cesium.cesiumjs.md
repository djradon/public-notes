---
id: wfxjhap9zcdg7a58wv83l5i
title: CesiumJS
desc: 'Open source 3D visualization for the web'
updated: 1700508476097
created: 1680428982835
---

## Features

- Time-dynamic visualization
- 3D tiles and models
- vectors and geometry
- supports: [[prdct.czml]]

### Co-ordinates

- Coordinates in CesiumJS are expressed in [ECEF](https://en.wikipedia.org/wiki/ECEF) using the [Cartesian3](https://cesium.com/learn/cesiumjs/ref-doc/Cartesian3.html) class. In this system, the origin (0, 0, 0) is the center of Earth.

This is why we use `Cartesian3.fromDegrees` to convert from longitude, latitude, and height to X, Y, and Z in ECEF.

The height in CesiumJS is in meters relative to the WGS84 ellipsoid. We’ve preprocessed the radar data to convert the heights from feet relative to mean sea level to meters relative to the ellipsoid.

## Learning Resource

- https://cesium.com/learn/cesiumjs-learn/
- https://cesium.com/learn/cesiumjs-learn/cesiumjs-flight-tracker/
  - "you can later extend this code to parse the original data or even visualize live air traffic as samples are passed to your app from a server"

## References

- https://community.cesium.com/t/vector-data-from-database-postgis/889
  - Q: "I try to pull my vector data(points and lines) from my PostGIS database and render it on the top of base map. Any API to connect the database and render new features on the top of map?"
    - A: "use GeoServer and display the data in Cesium using a WMS layer"
- https://community.cesium.com/t/polygon-with-height-data-to-3d/4406
  - "Cesium has support for geojson directly, so depending on the complexity, you may be able to simply load in the generated geojson file. Here is an example for how to add it to Cesium: http://cesiumjs.org/Cesium/Apps/Sandcastle/index.html?src=GeoJSON%20and%20TopoJSON.html&label=DataSources "