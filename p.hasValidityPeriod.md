---
id: pS7NsvzlKin7hnc3UMpBz
title: hasValidityPeriod
desc: ''
updated: 1636474973107
created: 1635722197605
---



- [[p.hasDomain]] [[c.statement]]
- [[p.hasRange]] [[c.timeperiod]]

## Notes

- until there's a standard for expressing "infinite interval boundaries", I'm just going to follow @Meno-Hochschild and [use a "double dot" on either side of the solidus](https://stackoverflow.com/questions/48696238/is-it-possible-to-represent-and-open-ended-time-interval-with-iso-8601)
- of course, if there's only a single date-fragment, you can assume that's the start time, and end time is either open or unknown
- it we be nice to be able to express "validity until at least" and "validity since at least", maybe can be captured nicely with "hasValidityPoint"
- kinda need "hasInvalidityPeriod" and "hasInvalidityPoint" too
