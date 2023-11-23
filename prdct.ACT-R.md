---
id: 1G76xhabSwgBpVHCvcB2f
title: ACT-R
desc: a cognitive architecture
updated: 1700349232117
created: 1637813722983
---

- [[c.software.cognitive-architecture]]
- written-in:   [[t.cs.languages.lisp]]
- [[p.hasSite]] http://act-r.psy.cmu.edu/
- [[p.hasSense]]
  - [[p.instanceOf]] [[Cognitive Architecture|t.cs.ai.cognitive-architecture]]
  - a theory for simulating and understanding human cognition

## Features

ACT-R’s main components are:

    modules,
    buffers,
    pattern matcher.

Modules

There are two types of modules:

    perceptual-motor modules, which take care of the interface with the real world (i.e., with a simulation of the real world), The most well-developed perceptual-motor modules in ACT-R are the visual and the manual modules.
    memory modules.

There are two kinds of memory modules in ACT-R:

    declarative memory , consisting of facts such as Washington, D.C. is the capital of United States, France is a country in Europe, or 2+3=5, and
    procedural memory, made of productions. Productions represent knowledge about how we do things: for instance, knowledge about how to type the letter “Q” on a keyboard, about how to drive, or about how to perform addition.

Buffers

ACT-R accesses its modules (except for the procedural-memory module) through buffers. For each module, a dedicated buffer serves as the interface with that module. The contents of the buffers at a given moment in time represents the state of ACT-R at that moment.
Pattern Matcher

The pattern matcher searches for a production that matches the current state of the buffers. Only one such production can be executed at a given moment. That production, when executed, can modify the buffers and thus change the state of the system. Thus, in ACT-R cognition unfolds as a succession of production firings.

ACT-R Structure

ACT-R is a hybrid cognitive architecture. Its symbolic structure is a production system; the subsymbolic structure is represented by a set of massively parallel processes that can be summarized by a number of mathematical equations. The subsymbolic equations control many of the symbolic processes. For instance, if several productions match the state of the buffers, a subsymbolic utility equation estimates the relative cost and benefit associated with each production and decides to select for execution the production with the highest utility. Similarly, whether (or how fast) a fact can be retrieved from declarative memory depends on subsymbolic retrieval equations, which take into account the context and the history of usage of that fact. Subsymbolic mechanisms are also responsible for most learning processes in ACT-R.