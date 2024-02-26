---
id: NBKV23oxekesy2Jc7gK2X
title: Go (Language)
desc: ''
updated: 1708974569944
created: 1638032252097
---

- [[p.coreferences.main]] #go 

## Resources

- Does Go support [[t.cs.multiple-inheritance]]? https://groups.google.com/g/golang-nuts/c/x8GEbutPhuc
- [Golang concepts from an OOP point of view](https://github.com/luciotato/golang-notes/blob/master/OOP.md)

## Issues

- No ability to dynamically import symbols from shared libraries. "Go applications are always single binaries that contain all of the code needed to run that program. The application may read external configuration or files or whatnot, but no code is read from external files. This makes a lot of sense if you’re writing self-contained applications like web apps, but anything that requires extensibility suddenly requires you perform some insane workarounds. The most common workaround is for the main process to spawn a subprocess running a whole other application and for the two to communicate via RPC."

## References

- https://peterfraedrich.medium.com/its-time-for-a-new-programming-language-f04e24704101