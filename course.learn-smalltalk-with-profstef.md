---
id: cx02lb6iehip5f6o42dpcth
title: Learn Smalltalk with Profstef
desc: ''
updated: 1695928512817
created: 1695920455913
---

- #url https://amber-lang.net/learn.html

## Highlights

- "Literal arrays are created at parse time:" 
  - #( 1 2 3 #(4 5 6))
- "Dynamic Arrays are created at execution time:" 
  - { (2+3) . (6*6) }
- "Messages are sent to objects. There are three types of message: Unary, Binary and Keyword."
  - unary: anObject aMessage 
  - binary: anObject + anotherObject"
  - keyword: anObject akey: anotherObject akey2: anotherObject2
  - "Unary messages are executed first, then binary messages and finally keyword messages:
    - "Between messages of similar precedence, expressions are executed from left to right"
- "; is the cascade operator. It's useful to send message to the SAME receiver"
- Blocks [ ] are anonymous methods that can be stored into variables and executed on demand.
- |b| is the declaration of a variable named 'b' and that ':=' assigns a value to a variabl