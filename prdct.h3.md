---
id: eqpfbn6ppca6xxa2dpyjmuk
title: H3
desc: ''
updated: 1699990424527
created: 1696438166743
---

- url: https://h3geo.org
- repo: https://github.com/uber/h3
- #docs https://h3geo.org/docs/

## [[p.supports]]

- #javascript with [[prdct.h3.js]]
- #java with [[prdct.h3.java]]
- [[prdct.postgres]] via [[prdct.postgres.h3-pg]]

## Descriptions

- Since it is not possible to tile the icosahedron with only hexagons, we chose to introduce twelve pentagons, one at each of the icosahedron vertices. These vertices were positioned using the spherical icosahedron orientation by R. Buckminster Fuller, which places all the vertices in the water. This helps avoid pentagons surfacing in our work.
- H3 supports sixteen resolutions. Each finer resolution has cells with one seventh the area of the coarser resolution. Hexagons cannot be perfectly subdivided into seven hexagons, so the finer cells are only approximately contained within a parent cell.
- "Hexagons (unlike say, squares or triangles) approximate various shapes like neighborhoods and city blocks more accurately."[1]

## Features

- [flow modeling](https://h3geo.org/docs/highlights/flowmodel)
  - H3 can create indexes that refer to the movement from one cell to a neighbor. These directed edge indexes share the advantages with their cell index counterparts, such as being 64 bit integers. The use of directed edges makes it possible to associate a weight with a movement in the grid.

## #related

- https://github.com/clupasq/h3-viewer

## Comparison

- [[prdct.s2-geometry|S2 Geometry]] test
  - https://h3geo.org/docs/comparisons/s2
- [[prdct.geohash]]
  - https://h3geo.org/docs/comparisons/geohash
- [[prdct.hexbin]]


## Resources

- https://www.uber.com/blog/h3/
- https://betterprogramming.pub/playing-with-ubers-hexagonal-hierarchical-spatial-index-h3-ed8d5cd7739d
- [1]: https://afi.io/blog/uber-h3-js-tutorial-how-to-draw-hexagons-on-a-map/
  - mentions [[prdct.react-map-gl]]