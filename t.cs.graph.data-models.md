---
id: aMTKbThufGmayEXkgkOUg
title: Data Models
desc: ''
updated: 1728865335007
created: 1638670758455
---



- resources: 
  - https://web.stanford.edu/class/cs520/2020/notes/What_Are_Graph_Data_Models.html
    - [[p.hasHighlight]]
      - A graph data model is not the most appropriate choice when the application contains primarily numeric data, and the reliance on only binary relationships is limiting. For example, the relational model is more effective in capturing timeseries data such as evolution of the population of a country. Even though we can represent such data using a graph, but it results in a huge number of triples without necessarily giving us advantages of better conceptual understanding and/or faster query performance through graph traversals. There are many relationships that cannot be naturally represented using binary relations. For example, between relation that captures that an object A is between two other objects B and C is inherently a ternary relationship. A ternary relationship can be transformed into a set of binary relationships using the reification technique, but by doing so, we lose the advantage of better conceptual understanding that we get from the graph data model. Graphs are also not the most natural representation for mathematical equations and chemical reactions where easy to understand domain specific representations exist.
