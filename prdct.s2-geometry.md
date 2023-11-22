---
id: kzmijzpawjw5x22nz8ac76c
title: S2 Geometry
desc: 'a library for spherical geometry that aims to have the same robustness, flexibility, and performance as the very best planar geometry libraries'
updated: 1680430443407
created: 1680430426947
---

- url: https://s2geometry.io
- #topic [[t.math.geometry]] 

## Resources

- https://s2geometry.io/resources/earthcube

## Highlights

- In S2, points are represented internally as unit-length vectors (points on the surface of a three-dimensional unit sphere) as opposed to traditional (latitude, longitude) pairs. This is for two reasons:

Unit vectors are much more efficient when working with geodesic edges. Using (latitude, longitude) pairs would require constantly evaluating trigonometric functions (sin, cos, etc), which is slow even on modern CPU architectures.

Unit vectors allow exact geometric predicates to be evaluated efficiently. To do this with (latitude, longitude) pairs, you would essentially need to convert them to the unit vector representation first.
