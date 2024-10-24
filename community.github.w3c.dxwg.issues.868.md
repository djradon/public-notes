---
id: v1zghmhfcl42l1imfh6fft2
title: 'Dataset series'
desc: ''
updated: 1729789337101
created: 1729789337101
---

- https://github.com/w3c/dxwg/issues/868

## Highlights

@der: 

- "it is relatively rare for a dataset to be a unitary thing which be downloaded in its entirety. More typically the non-realtime datasets we see comprise a series of updates (annual, quarterly, monthly etc as determined by some release cycle). Where possible we provide data services and dumps for the whole series. However, both users and publishers want to explicitly see the series of updates as individual elements they can separately download but regard the collection of those updates as a single dataset with common metadata and want the data, and presentation of it, to reflect that."

- want to treat each of our resources as an instance of both dcat:DatasetSeries and dcat:Dataset. That way we could give a distribution (and extent) for the overall aggregate as well as distributions for the individual elements within the series. 