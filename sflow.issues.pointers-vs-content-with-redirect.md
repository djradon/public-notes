---
id: 48yol3ey8sskt4wwkruw8s3
title: Pointers Vs Content with Redirect
desc: ''
updated: 1750444862333
created: 1750295836745
---



## claude.3.sonnet

**On the pointer data inclusion dilemma** (.8) - you've identified a real tension:

**Include data:** Convenient for users, but encourages sloppy referencing
**Exclude data:** Forces precision, but creates friction

The minefield is real because you're trying to balance:
- Usability (people want immediate data)
- Semantic clarity (specific references should be explicit)
- Caching/performance (duplicate data vs extra requests)

**Middle ground option** (.6): What if pointers return a **minimal subset** of the target data - just enough for basic identification/context, plus clear links to the full versioned dataset? Like:

```turtle
<https://djradon.github.io/ns/dave-richardson/> 
  rdfs:label "Dave Richardson" ;
  rdfs:seeAlso <https://djradon.github.io/ns/dave-richardson/personal-info/v3> ;
  prov:wasDerivedFrom <https://djradon.github.io/ns/dave-richardson/personal-info/v3> .
```

This gives enough for humans to understand what they found, but forces applications to use versioned IRIs for substantial data access (.7).

Still feels like you're designing something without clear precedent though - most Linked Data doesn't attempt this level of comprehensive dereferenceability.