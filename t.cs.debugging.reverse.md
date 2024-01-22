---
id: oj4vevko8u2q5f1ulf1ycj8
title: Reverse Debugging
desc: ''
updated: 1705954143862
created: 1705954063135
---

## History

It all started with Smalltalk-76, developed in 1976 at [Xerox PARC](https://en.wikipedia.org/wiki/PARC_(company)). ([Everything](https://en.wikipedia.org/wiki/Graphical_user_interface) [started](https://en.wikipedia.org/wiki/Computer_mouse) [at](https://en.wikipedia.org/wiki/Ethernet) [PARC](https://en.wikipedia.org/wiki/WYSIWYG) 😄.) It had the ability to retrospectively inspect checkpointed places in execution. Around 1980, MIT added a “retrograde motion” command to its [DDT debugger](https://en.wikipedia.org/wiki/Dynamic_debugging_technique), which gave a limited ability to move backward through execution. In a 1995 paper, MIT researchers released ZStep 95, the first true reverse debugger, which recorded all operations as they were performed and supported stepping backward, reverting the system to the previous state. However, it was a research tool and not widely adopted outside academia.

ODB, the [Omniscient Debugger](https://omniscientdebugger.github.io/ODBUserManual.html), was a Java reverse debugger that was introduced in 2003, marking the first instance of time-travel debugging in a widely used programming language. [GDB](https://en.wikipedia.org/wiki/GNU_Debugger) (perhaps the most well-known command-line debugger, used mostly with C/C++) added it in 2009.

Now, time-travel debugging is available for [many](https://github.com/rr-debugger/rr/wiki/Related-work) languages, platforms, and IDEs, including:

-   [Replay](https://www.replay.io/) for JavaScript in Chrome, Firefox, and Node, and [Wallaby](https://wallabyjs.com/docs/intro/time-travel-debugger.html) for tests in Node
-   [WinDbg](https://learn.microsoft.com/en-us/windows-hardware/drivers/debugger/time-travel-debugging-overview) for Windows applications
-   [rr](https://rr-project.org/) for C, C++, Rust, Go, and others on Linux
-   [Undo](https://undo.io/) for C, C++, Java, Kotlin, Rust, and Go on Linux
-   Various extensions (often rr- or Undo-based) for Visual Studio, VS Code, JetBrains IDEs, Emacs, etc.

## References

- https://temporal.io/blog/time-travel-debugging-production-code