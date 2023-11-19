---
id: izh965ltyaoy8ahsbssda0x
title: CZML
desc: 'JSON-based format for describing a time-dynamic graphical scene, primarily for display in a web browser'
updated: 1700418672122
created: 1700418086377
---

- related: [[prdct.czml-writer]]

## Description

- "A [CZML document](https://github.com/AnalyticalGraphicsInc/czml-writer/wiki/CZML-Structure) is an array of ‘[packet](https://github.com/AnalyticalGraphicsInc/czml-writer/wiki/Packet)’ elements, each of which represents one object in the Cesium visualization scene (e.g., a cylinder in our case), and its associated properties (e.g., color, position, availability). It is worth mentioning that the [Cesium Sandcastle site](https://sandcastle.cesium.com/) provides a fair number of live examples that can be used to learn CZML."

## Features

- "describe properties that change value over time. For example, a line can be red for one interval of time and blue for another. Clients are also expected to be able to interpolate over time-tagged samples. If the position of a vehicle is specified at two times, the client can accurately display the location of the vehicle in between those two times by using a CZML-specified interpolation algorithm. Every property is time-dynamic."
- 

## Comparison

## vs [[prdct.kml]]

## Resources

- https://cesium.com/blog/2018/03/21/czml-time-animation/