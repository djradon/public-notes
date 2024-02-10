---
id: BJZRQTTff77MsBb32oNf5
title: Godot
desc: ''
updated: 1707497422153
created: 1637591669334
---

[[c.software.game-engine]]

- [[p.hasRepository]] https://github.com/godotengine/godot
- [[p.hasSite]] https://godotengine.org/
- [[p.builtWith]] #c++
- [[p.hasScriptingLanguage]] 
  - [[t.cs.languages.gdscript]] 
  - [[t.cs.languages.C-sharp]]
  - #c++
  - typescript via https://github.com/GodotExplorer/ECMAScript and [[prdct.quickjs]]
  - #rust
  - #python via [PythonScript](https://godotengine.org/asset-library/asset/179)


## Features

- publish to web
  - [[c.issue]]  ^x343t4fze5lf
    - t.2023.10.09 Projects written in C# using Godot 4 currently cannot be exported to the web. To use C# on web platforms, use Godot 3 instead.
    - Godot 4's HTML5 exports currently cannot run on macOS and iOS due to upstream bugs with SharedArrayBuffer and WebGL 2.0.
- dynamic execution
  - @tool makes scripts execute in the editor  https://docs.godotengine.org/en/stable/tutorials/plugins/running_code_in_the_editor.html ^lk1riz8a7a5e
    - e.g. If your player doesn't use a sprite, but draws itself using code, you can make that drawing code execute in the editor to see your player.
  - https://ask.godotengine.org/34626/dynamic-code
- [[prdct.wasm]] [support](https://docs.godotengine.org/en/acctable/contributing/development/compiling/compiling_for_web.html) via [[prdct.emscripten]]
  - Using Go for WebAssembly offers several advantages. First, Go provides a familiar and straightforward programming environment for web developers, making it easy to transition from traditional Go development to web development.
  - Secondly, Go’s performance and concurrency features are well-suited for building efficient web applications that can handle heavy workloads.
  - Finally, the combination of Go and WebAssembly allows for cross-platform compatibility, enabling the deployment of applications on various browsers without the need for plugins or additional dependencies.
- [[c.software.entity-component-system]] 

## Cons

- as of early 2024, no c# support for web platform
- does not support exception handling https://heroiclabs.com/docs/nakama/client-libraries/godot/ 
- @hendrik-mans: "I love that Godot exists, but I hate it so much
It is what it is, and if you take it as just that, it's alright, but as soon as you look at the terrible source code or otherwise interact with the project or the people in it, it gets so painful.
My favorite Godot experience is how, after reporting something that's obviously broken, or opening a proposal for a new feature/change that I think might be useful because I use them in other engines, someone from the core team will always end up telling me how the bug/broken behavior might, in fact, be good, or how the thing that literally every other engine does is in fact bad
How about a mute button that will disable sound when running the game/a scene? No, the user can just drop down their PC's volume for that!
How about an icosphere geometry generator? lol what's an icosphere, that kinda looks funny, juse use a normal sphere!
Shader code can't shadow global names in local variable names! Oh yeah we don't know if that is on purpose but it feels like if they can do that, it might confuse people
But your language claims to be GLSL compatible, and in GLSL you can shadow global names! Oh yeah well it's still confusing
How about being able to scale rigidbodies? THAT'S IMPOSSIBLE!!!!!
No, it's not, literally every engine supports it (by internally scaling colliders)! oh yeah? well, that's kinda confusing. All rigidbodies should be the same size! If you need an object in several different sizes, just make copies of the scene and adjust the colliders manually!
etc. etc. etc.
It really is a terrible terrible terrible piece of software and the only chance one has at maybe enjoying it is to just think of fluffy little kittens every time you encounter something that's broken or bad. But do not, I repeat, do NOT engage with the project."
  - https://discord.com/channels/844566064281026600/850335072242237470/1175129150068109367

## Resources

- https://github.com/abmarnie/godot-architecture-organization-advice

## References

- https://godotengine.org/article/whats-new-in-csharp-for-godot-4-0/
- https://godotengine.org/article/why-isnt-godot-ecs-based-game-engine/
- https://programminghaven.home.blog/2020/01/30/designing-a-loosely-coupled-gdscript/