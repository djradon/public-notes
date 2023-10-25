---
id: BJZRQTTff77MsBb32oNf5
title: Godot
desc: ''
updated: 1698262518363
created: 1637591669334
---

[[c.Software.Game-Engine]]

- [[p.hasRepository]] https://github.com/godotengine/godot
- [[p.hasSite]] https://godotengine.org/
- [[p.builtWith]] #c++
- [[p.hasScriptingLanguage]] 
  - [[t.cs.languages.GDScript]] 
  - [[t.cs.languages.C-sharp]]
  - #c++
  - #typescript via https://github.com/GodotExplorer/ECMAScript and [[prdct.quickjs]]
  - #rust
  - #python via [PythonScript](https://godotengine.org/asset-library/asset/179)


## Features

- publish to web
  - [[c.Issue]]  ^x343t4fze5lf
    - #t.2023.10.09 Projects written in C# using Godot 4 currently cannot be exported to the web. To use C# on web platforms, use Godot 3 instead.
    - Godot 4's HTML5 exports currently cannot run on macOS and iOS due to upstream bugs with SharedArrayBuffer and WebGL 2.0.
- dynamic execution
  - @tool makes scripts execute in the editor  https://docs.godotengine.org/en/stable/tutorials/plugins/running_code_in_the_editor.html ^lk1riz8a7a5e
    - e.g. If your player doesn't use a sprite, but draws itself using code, you can make that drawing code execute in the editor to see your player.
  - https://ask.godotengine.org/34626/dynamic-code
- [[prdct.wasm]] [support](https://docs.godotengine.org/en/stable/contributing/development/compiling/compiling_for_web.html) via [[prdct.emscripten]]
  - Using Go for WebAssembly offers several advantages. First, Go provides a familiar and straightforward programming environment for web developers, making it easy to transition from traditional Go development to web development.
  - Secondly, Go’s performance and concurrency features are well-suited for building efficient web applications that can handle heavy workloads.
  - Finally, the combination of Go and WebAssembly allows for cross-platform compatibility, enabling the deployment of applications on various browsers without the need for plugins or additional dependencies.
- [[c.Software.Entity-Component-System]] 

## [[c.Con]]

- does not support exception handling https://heroiclabs.com/docs/nakama/client-libraries/godot/ 

## References

- https://godotengine.org/article/whats-new-in-csharp-for-godot-4-0/
- https://godotengine.org/article/why-isnt-godot-ecs-based-game-engine/
- https://programminghaven.home.blog/2020/01/30/designing-a-loosely-coupled-gdscript/