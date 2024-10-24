---
id: u0v40nny2bjn315zi2szi6i
title: 'Model Series of Data as Distributions of a single Dataset'
desc: ''
updated: 1729790875721
created: 1729790875721
---

- https://github.com/w3c/dxwg/issues/1429

## Highlights

### riccardoAlebrtoni

It might be worth noting that the current DCAT Editor Draft and the second DCAT working draft acknowledge some flexibility on what to consider as items of [dcat:datasetSeries](https://www.w3.org/TR/2021/WD-vocab-dcat-3-20210504/#Class:Dataset_Series), which already includes the use of Distributions in place of Datasets.

Indeed, the property [dcat:inSeries](https://www.w3.org/TR/2021/WD-vocab-dcat-3-20210504/#Property:dataset_in_series), which links the items to data series, has no domain specified, and its usage note says

`Normally, child datasets in dataset series are represented as dcat:Dataset. The use of dcat:Distribution for typing child datasets is however recognized as a possible alternative, whenever it addresses more effectively the requirements of a given application scenario.`

I think we can distinguish between informatively equivalent and non-informative equivalent distributions using the properties dcat:distribution and dcat:inSeries.  
I would expect the informative equivalence holds between distributions of the same dataset, i.e. the distribution linked to the same dataset via dcat:distribution, not between distributions used as items in a dataset Series, i.e., distributions linked via dcat:inSeries to a dcat:datasetSeries.

### matthiaspalmer

```turtle
ex:dataset1 a dcat:Dataset ;
     dcat:distribution ex:distribution1, ex:distribution2 .

ex:distribution1 a dcat:Distribution ;
     dcterms:title  "Access via CSV files" ;
     dcat:downloadURL  ex:file1,ex:file2 .

ex:file1 dcterms:title "Budget 2019" .
ex:file2 dcterms:title "Budget 2020" .

ex:distribution2 a dcat:Distribution ;
     dcterms:title "Access via a JSON based API" ;
     dcat:accessURL ex:API
```

This approach has the following merits:

1.  The distributions are comparable, they contain the same data.
2.  The amount of duplication of metadata is minimal
3.  It is relatively easy to explain to data providers what to do
4.  Providing multiple distributions (e.g. API and file based access) is obvious
5.  More information can be provided on each file if there is a need.
6.  There won't be any unneccessary pollution in dataportals of many datasets

It could be argued that repeating the dcat:downloadURL is bad, that it is not intended to be used that way. The specification says "the downloadable file" which indeed seems to indicate there should be a cardinality of one.

However, I think it should be investigated if it can easily be tweaked to be compliant.
For instance, allowing a dcat:downloadPartURL as an alternative to dcat:downloadURL, maybe introducing a class like dcat:File and just suggesting that it is allowed to provide a dcterms:title on it.