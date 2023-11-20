---
id: pv2vqohj87ascifluhbxkfe
title: Geoserver
desc: 'reference implementation of the Open Geospatial Consortium (OGC) Web Feature Service (WFS) and Web Coverage Service (WCS) standards, as well as a high performance certified compliant Web Map Service (WMS), compliant Catalog Service for the Web (CSW) and implementing Web Processing Service (WPS)'
updated: 1700507558887
created: 1700415900498
---

- [[c.software.gis]]
- url: https://geoserver.org/
- repo: https://github.com/geoserver/geoserver
- written-in: java

## Issues

- no [[t.geo.ecef]] or 3d support?
  - https://gis.stackexchange.com/questions/244737/how-can-i-project-earth-centered-cartesian-coordinates-epsg4978-to-lat-lon-wi
  - "because JTS Topology Suite, which is an important component of GeoServer, does not support 3D spatial operations, it also does not support solid geometries." [1]
    - 

## Resources

- [1]: [[ar.development-of-an-extension-of-geo-server-for-handling-3-d-spatial-data]]