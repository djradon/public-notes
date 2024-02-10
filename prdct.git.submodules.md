---
id: dfr8ai66wk9qjp63725k8f7
title: Submodules
desc: ''
updated: 1707497236353
created: 1707496900016
---

Git submodules are a way to have another repository inside your own repository. All the benefits of code sharing, none of the fuss. Well, maybe some of the fuss. Because git’s implementation of submodules leaves something to be desired.

The first and most obvious problem with Submodules is when you pull f

```
git config --global submodule.recurse 
```

And second you may have to init the submodule once you clone the project onto another computer.

```
git submodule update --init --recursive
```

And even after this there does not appear to be a way to keep them pointed at the `HEAD` commit which makes committing to them a bit more difficult.

## References

- https://medium.com/lost-but-coding/just-say-no-to-monorepos-8f288fd0eeb1