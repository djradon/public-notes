---
id: eqpfbn6ppca6xxa2dpyjmuk
title: H3
desc: ''
updated: 1696438766874
created: 1696438166743
---

- #url https://h3geo.org
- #repo https://github.com/uber/h3
- #docs https://h3geo.org/docs/
## [[c.Description]]

- Since it is not possible to tile the icosahedron with only hexagons, we chose to introduce twelve pentagons, one at each of the icosahedron vertices. These vertices were positioned using the spherical icosahedron orientation by R. Buckminster Fuller, which places all the vertices in the water. This helps avoid pentagons surfacing in our work.
- H3 supports sixteen resolutions. Each finer resolution has cells with one seventh the area of the coarser resolution. Hexagons cannot be perfectly subdivided into seven hexagons, so the finer cells are only approximately contained within a parent cell.

## [[c.Resource]]

- https://www.uber.com/blog/h3/