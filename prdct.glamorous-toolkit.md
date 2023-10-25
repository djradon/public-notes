---
id: j2nauxu4s9cnuheizcz8fmy
title: Glamorous Toolkit
desc: >-
  a live notebook. A fancy code editor. A software analysis platform. A data
  visualization engine. A knowledge management system. All in one.
updated: 1698252759231
created: 1650122141316
---

- [[c.Software.Computational-Notebook]] [[c.Software.IDE]]
- [[p.hasRepository]] https://github.com/feenkcom/gtoolkit
- [[c.UseCase]]
  - [[t.cs.sd.specification]]
  - [[t.cs.sd.assessment]]
  - [[t.cs.data.visualization]]
- [[p.writtenIn]] [[t.cs.languages.smalltalk.pharo]]

## [[p.hadDefinition]]

- "live literate programming environment"
  - [[p.attributedTo]] @gilad-bracha
- "While you write your application you're also writing the tools which make it easy to write and debug your application. In Lisp you do this through molding the language; in GToolkit you do this through molding the IDE."
  - https://news.ycombinator.com/item?id=33267518
- "It's a suite of extensions of the Pharo Smalltalk environment that are tailored for modeling behaviour and data in multiple ways, such that you can build your own toolkit for your own problem domain."


## Features

- Rust enabled runtime
  - The Glamorous Toolkit virtual machine is formed by a Rust runtime that wraps and runs the Pharo virtual machine as a library in a separate operating system thread. The runtime also comes with Rust plugins and with an infrastructure for creating Rust plugins.
- supports [[t.cs.sd.example-driven-development]], which is like [[t.cs.sd.test-driven-development]], but supports [[t.cs.sd.live-tutorials]]

## [[c.UseCase]]

- [[c.Software.Knowledge-Base]] for system documentation
- Data Explorer


## [[c.Con]]

- "To get a living system + its real time perspectives and embedded live documentation it seems you must program the system in Pharo." ?

## [[c.Resource]]

- https://medium.com/feenk/one-rendering-tree-918eae49bcff
- [+] https://lepiter.io/feenk/glamorous-toolkit-and-pharo-9q25tavxwfq6z1drwvegd5u9o/