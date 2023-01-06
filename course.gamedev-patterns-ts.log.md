---
id: dk31m76ibadozhqu800qbl9
title: Log
desc: ''
updated: 1673017741397
created: 1672667912959
---

## #t.2023.01.01
  
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
  - https://stackoverflow.com/questions/51439843/unknown-vs-any [[p.stated]] 
    - "unknown is I don't know; any is I don't care"
    - "any value is assignable to unknown; however, unlike any, you cannot access any properties on values with the type unknown, nor can you call/construct them. Furthermore, values of type unknown can only be assigned to unknown or any."
- [[prdct.typescript.barrel-files]] might be over-used

## #t.2023.01.02

- [-] would seem to be [[t.cs.game.loop.recursive]], but v8 took out [[t.cs.recursion.tail-call-optimization]]
- Game has its own entities and all components; both can be awoken.

## #t.2023.01.05

- Having a tool that can change the behavior of the game without diving too deep into the code can be a huge time saver.

## #t.2023.01.06

- "Note, I don’t have access to Grid instance since it’s created and encapsulated by the Game. But I can rely on Grid.prototype to access Grid methods without an actual instance."
- "The Component interface requires specifying which entity the component can be attached to. In this case, it’s the Node entity."