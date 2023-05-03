---
id: 5eue0qbos8n15rtpd3i55xb
title: Abstract Meaning Representation
desc: 'Each AMR is a single rooted, directed graph.'
updated: 1682978720028
created: 1682976801246
---

- #url https://amr.isi.edu https://catalog.ldc.upenn.edu/LDC2020T02

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