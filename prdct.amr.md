---
id: 5eue0qbos8n15rtpd3i55xb
title: Abstract Meaning Representation
desc: 'AMR captures the rough meaning of a sentence in a single, traversable directed acyclic graph.'
updated: 1694642336962
created: 1682976801246
---

- #url https://amr.isi.edu https://catalog.ldc.upenn.edu/LDC2020T02
- [[p.hasSpecification]] https://github.com/amrisi/amr-guidelines/blob/master/amr.md


## [[c.Con]]

* It does not represent quantifier scope, or even universal quantification at all.
* It does not represent co-references that cross sentence boundaries.
* It drops grammatical number, tense, aspect, quotation marks, etc.
* It does not deeply capture many noun-noun or noun-adjective relations.
* It does not include deep frames such as Earthquake (with roles for magnitude, epicenter, casualties, etc) or Pregnancy (with roles for mother, father, baby gender, time since inception, etc). AMR 1.2 looks forward to AMR 2.0!

## [[c.Example]]

- "About 14,000 people fled their homes at the weekend after a local tsunami warning was issued, the UN said on its Web site"
```
(s / say-01
  :ARG0 (g / organization
          :name (n / name
                  :op1 "UN"))
  :ARG1 (f / flee-01
          :ARG0 (p / person
                  :quant (a / about
                           :op1 14000))
          :ARG1 (h / home
                  :poss p)
          :time (w / weekend)
          :time (a2 / after
                  :op1 (w2 / warn-01
                         :ARG1 (t / tsunami)
                         :location (l / local))))
  :medium (s2 / site
            :poss g
            :mod (w3 / web)))
```