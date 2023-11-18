---
id: IOiipJ45yPMxjvGGiZJdM
title: Redux JS
desc: javascript state management
updated: 1700262960655
created: 1640057990310
---

- [[c.software.state-store]]
- [[p.vs]] [[prdct.react]]
  - [[p.hasSource]] 
    - https://www.fireup.pro/blog/redux-vs-react-context-which-should-you-use
    - https://changelog.com/posts/when-and-when-not-to-reach-for-redux
- [[p.compatibleWith]] [[prdct.svelte]]
- [[p.integratesWith]] [[prdct.svelte]]
- similar-to: [[prdct.mobx]]

## Use Cases

- server-side state, see https://github.com/mobxjs/mobx/issues/1922

## Principles

- "Instead of mutating the state directly, you specify the mutations you want to happen with plain objects called actions. Then you write a special function called a reducer to decide how every action transforms the entire application's state... It also enables very powerful developer tools, because it is possible to trace every mutation to the action that caused it. You can record user sessions and reproduce them just by replaying every action."
  - https://redux.js.org/introduction/getting-started

## Resources

- https://svelte.dev/repl/b41141c04f1140b687ce5f1bb3c036b9?version=3.48.0
- http://orta.io/notes/games/phaser-redux
- http://orta.io/notes/games/phaser-redux