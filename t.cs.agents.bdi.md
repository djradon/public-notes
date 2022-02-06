---
id: w2aHesH8f6LrctkdYTrtr
title: 'Belief, Desire, Intention'
desc: ''
updated: 1637670053209
created: 1637669903112
---


## Simplified BDI Algorithm

- [[p.hasSource]] https://www.inf.ed.ac.uk/teaching/courses/masws/lectures-14/16-full.pdf

```
Reason(B, D, I)
    while true do
        p <- next percept
        B <- revise(B, p)
        D <- options(B, I)
        I <- deliberate(B, D, I)
        P <- plan(B, I)
        execute(P)
```
