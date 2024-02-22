---
id: n22i4ms1hh3u9pl43ykev9h
title: Architecture Tricks Managing Behaviors in Time Space and Depth
desc: ''
updated: 1708635159347
created: 1708633650457
---

- presenter: @david-mark

## Overview

While the standard AI algorithms we all know (and love?) look good on paper, we often run up against barriers when we put them into practice. Usually, these barriers occur when NP-Hard problems clash with limitations on memory and processing cycles. Add in the necessity to allow for the simple, expandable creation and management of behaviors, and the scope of the problem expands significantly. This lecture will show three different tricks for helping AI solve difficult problems while staying manageable. Dino Dini will show how co-routines can help mitigate the "polling problem" in AI behavior. Luke Dicken will show how complex behavior planning can be done off-line and spliced at run-time as necessary. Dave Mark will show his "infinite axis" utility system that allows for the simple design and processing of modular reasoners. All three sections will give concrete takeaways that can be applied to a variety of AI applications. 

## Highlights

- if 
  - a change in state
  - dependent on the current state
  - when the "if" is executed
- when
  - a change in state
  - dependent on the resulting state
  - when a specified state change occurs
  - "computers are not really set up for the when"
  - typical solution is messages,
    - but you have to keep polling
- can have reusable behaviors if the language supports nestable coroutines
- but messages must be able to change the program counter
- mentions: PROC system

## Resources

- [[book.behavioral-mathematics-for-game-ai]]