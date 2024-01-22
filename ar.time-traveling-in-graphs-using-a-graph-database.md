---
id: plzqijn9u7758ktbdfajvh5
title: Time Traveling in Graphs Using a Graph Database
desc: ''
updated: 1705948591753
created: 1696474895633
---

- url: https://ceur-ws.org/Vol-1558/paper21.pdf

## Highlights

- Historical graph queries are graph queries applied at past snapshots. For example, a historical graph reacha- bility query may ask whether two nodes were reachable at some time interval in the past. 
- Historical time queries are graph queries that ask about the time point or the time interval that a query had a specific result. For example, a historical time reachability query may ask for the time point at which two nodes become reachable for the rst time. 
- Finally, historical top-k queries ask for the nodes that had a property for the longest period of time. For example, a his- torical top-k reachability query may ask for the k pairs of nodes that remained connected for the longest interval.

### single and multi edge representation

- the single-edge approach: the lifespan of a node or edge is modeled using a label (i.e., an attribute or property) of the corresponding node or edge. Figure 1 shows an example of edge lifespans represented by a single label of type String. For example, the co-authorship between authors A, C in 2010, and 2012, is represented by the edge with label "2010,2012". Graph evolution can be tracked by processing the node and edge lifespan labels. Thus, to obtain the graph snapshot Gt for a time point t, we get all edges and nodes and then keep only those edges and nodes whose lifespan label contains t.
  - for second-level precision, seems incredibly wasteful
- the multi-edge approach uses a different edge type between two nodes for each time point of the lifespan of the edge. For instance, in order to represent co-authorship between authors A, B, C in 2010, 2012, and 2014, we use three different labeled types of edges to connect A, B, and C.