---
id: wfxjhap9zcdg7a58wv83l5i
title: CesiumJS
desc: 'Open source 3D visualization for the web'
updated: 1700421482265
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