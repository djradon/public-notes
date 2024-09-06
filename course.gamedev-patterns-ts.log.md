---
id: dk31m76ibadozhqu800qbl9
title: Log
desc: ''
updated: 1725583654915
created: 1672667912959
---

## t.2023.01.01
  
- Why use getters in Javascript?
  - [[p.hasAnswers]]
    - "So if you decide to add this kind of extra logic to one of the existing object properties that is already being referenced, you can convert it to getter/setter style without altering the rest of the code that has access to that property."
      - https://stackoverflow.com/questions/42342623/why-use-getters-and-setters-in-javascript

    - "One difference is typeof will actually work as expected when using a getter, that is, it will return the actual type of the primitive returned by the getter, while using a method will always return function"
    - "if you have nested getters, you can call them transparently, which is something that comes in handy if you are navigating an object programmatically"
      - https://stackoverflow.com/questions/59569178/whats-the-point-of-a-javascript-getter-method
- Surprised that this code works:
```typescript
public AddComponent(component: IComponent): void {
    this._components.push(component)
    component.Entity = this
  }
```
  - [[p.hasAnswers]]
    - "Objects and arrays are pushed as a pointer to the original object . Built-in primitive types like numbers or booleans are pushed as a copy."
      - https://stackoverflow.com/questions/8660901/do-objects-pushed-into-an-array-in-javascript-deep-or-shallow-copy
- Why generics for functions?
  - https://www.typescriptlang.org/docs/handbook/2/generics.html
    - While using any is certainly generic in that it will cause the function to accept any and all types for the type of arg, we actually are losing the information about what that type was when the function returns. If we passed in a number, the only information we have is that any type could be returned. Instead, we need a way of capturing the type of the argument in such a way that we can also use it to denote what is being returned. Here, we will use a type variable, a special kind of variable that works on types rather than values.
```typescript
function identity<Type>(arg: Type): Type {
  return arg;
}
```
- [x] @greg-solo uses ".h.ts" for header files, but should probably be "[.d.ts](https://www.typescriptlang.org/docs/handbook/declaration-files/templates/module-d-ts.html)"
- `unknown` is typesafe version of `any`
  - https://stackoverflow.com/questions/51439843/unknown-vs-any :
    - "unknown is I don't know; any is I don't care"
    - "any value is assignable to unknown; however, unlike any, you cannot access any properties on values with the type unknown, nor can you call/construct them. Furthermore, values of type unknown can only be assigned to unknown or any."
- [[prdct.typescript.barrel-files]] might be over-used

## t.2023.01.02

- [-] would seem to be [[t.cs.game.loop.recursive]], but v8 took out [[t.cs.recursion.tail-call-optimization]]
- Game has its own entities and all components; both can be awoken.

## t.2023.01.05

- Having a tool that can change the behavior of the game without diving too deep into the code can be a huge time saver.

## t.2023.01.06

- "Note, I don’t have access to Grid instance since it’s created and encapsulated by the Game. But I can rely on Grid.prototype to access Grid methods without an actual instance."
- "The Component interface requires specifying which entity the component can be attached to. In this case, it’s the Node entity."
- I questions the utility of "We don’t have access to the instance of a component, but we can spy on its prototype."
- "Vector2D, as ECS or lifecycle methods, is a utility. It does not depend on the game"
- [[p.begsQuestion]] should the filename match the Class name?
  - [[p.hasAnswers]]
    - "Use kebab-case for all package, folder and file names." b/c packages can't have upper case
- "keep a constructor lean"
- ` can be used for string with variable substitution
- "Though neither Canvas nor CanvasLayer are singletons, static CanvasLayer ensures Canvas is instantiated only ones"

## t.2023.01.07

- [-] how does jest.mock('@/utils') work?
- integer check: v % 1 !== 0
- toThrowError is alias for toThrow and takes an optional RegEx, substring, error object or error class
- Partial: Constructs a type with all properties of Type set to optional. This utility will return a type that represents all subsets of a given type.
- [x] what does `type constr<T> = { new(...args: unknown[]): T }` (from entity.ts) do really?
  - it defines a new type
- `(team = Team.A): Fleet => new Fleet(team)` doesn't need parameter type because it's inferred from Team.A
- in locomotion, why have the position use pixels? probably just a design choice?

### https://medium.com/swlh/building-a-game-with-typescript-ship-and-locomotion-4f5969675993
- "it could use GetComponent, but we better cache the reference instead"
- "Node is not a core feature of the Ship (it’s neither its property nor field)"
- after breaking things, and messaging around with git, I did find a working commit in my own history.

## t.2023.01.08

- found it!, missing implementation of awake. wish I'd captured the test failures to confirm. 
- t.2023.01.08.13.23 wound up reverting to ships-3 and had to fix capitalization on Vector2D, so a bunch of git buggery, but I think I learned a little bit, and did my first merge to master
- "Since it’s read-only, a constructor is the only place we can do it"
- OK, failed at the same place... "Our code compiles again. Moreover, if you open it in the browser you can see this beautiful picture:" but this time I'm better off because
  - I'm looking at the browser console
  - figured it out, I missed the "grid" change change to the 
- [[read|p.read]] https://www.typescriptlang.org/docs/handbook/variable-declarations.html -- good, tricky
  - "var declarations are accessible anywhere within their containing function, module, namespace, or global scope... regardless of the containing block."
  - let declarations are block-scoped (aka lexical scoping)
  - loved [[t.cs.programming.temporal-dead-zone]]
  - `const` means no re-assignment (which is different from immutable, e.g. you can change properties)

### https://itnext.io/building-a-game-with-typescript-input-system-1-3-46d0b3dd7662

- there are no DOM elements within canvas
- how do nodes, ships get notified about events? Not [[t.cs.programming.patterns.observer]] because that couples game objects to the GameInputComponent.
  - instead, Onclick component
- I'm pleasantly surprised by how easy it is to dereference fields objects, e.g. `this.Entity.Entities`
- not sure how I feel about multiple files called draw.ts -- I feel like every filename should be unique
- `type` defines an alias to a type
- "When we say Function & { prototype: T } we mean that this “thing” must be a function AND should have a specific T type of parent constructor. In other words, it has to extend that T."
- had to do a separate `import { mockGridFactory } from '@/grid'`, didn't like it in with { Grid }

### https://blog.gregsolo.me/articles/building-a-game-with-typescript-pathfinding-and-movement-17-introduction

- !@#$ capitalization (vector2D folder vs vector2d file)

## t.2023.01.09

### https://blog.gregsolo.me/articles/building-a-game-with-typescript-pathfinding-and-movement-27-highlighting-locomotion-range

- Neighbors[] would not be readonly in my engine because it's fractal-like, invents itself as it goes along
- pre-decrement useful for recursion `const newRange = --range`
- recursion can be done with map!
- I'm just realizing now that @greg-solo capitalizes his public objects and all method names!?
  - makes his methods stand out
  - [x] am I crazy
    - @rvk confirmed

## t.2023.01.10

### https://blog.gregsolo.me/articles/building-a-game-with-typescript-pathfinding-and-movement-37-graph-and-priority-queue

- [[Type Assertions|t.cs.languages.typescript.type-assertions]] in the interface method signature can be linked/referenced internally, e.g. `export interface IPriorityQueue<T>` and `Enqueue(item: T, priority: number): void` means that the implementing class has to have identical type assertion in both places

## t.2023.01.11

### https://blog.gregsolo.me/articles/building-a-game-with-typescript-pathfinding-and-movement-57-finding-the-path

- [[p.learned]] [[t.math.geometry.taxicab-geometry]]
- [repeating ourselves](https://vscode.dev/github/djradon/gamedev-patterns-ts/blob/cca466d5cb27fafe06de0f08a958434b9bfc9f87/src/fleet/fleet.ts#L45-L46): 
```javascript
activeShip.IsActive = true
this._grid.ActiveShip = activeShip
```
- got stuck, the interactivity is broken, don't have the motivation to find out where, given movement-pathfinding-5 is just sitting there.
- any change to the source starts the thing over from the beginning; it's gonna be hard to test detailed scenarios


