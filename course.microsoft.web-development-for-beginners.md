---
id: o2vu2wH8CQEdqEmJU58XF
title: Web Development for Beginners
desc: even I probably should not start here
updated: 1698704342150
created: 1642483433436
---



- [[p.hasURL]] https://docs.microsoft.com/en-us/learn/paths/web-development-101/

- [[t.cs.web.accessibility]]
  - [[prdct.aria]]
  - "The controls for your page should be listed in the HTML source in the order in which you expect the page to be browsed, while relying on CSS to lay out the page visually to users."
- javascript
  - `let` is for block variables 
  - `var` is for function-scoped variables
  - initialize = declare + assign
  - `const` should get UPPER'd
    - The presence of const means the reference is protected from reassignment. But the value is not immutable and can change, especially if it's a complex construct like an object.
- [[t.cs.programming.readability]] 
  - camelCase your beautiful names
  - why not use verbs?
- [[t.cs.programming.functions.callbacks]]
  - no parens! including parens means call it now (and pass return value?)
- [[t.cs.programming.functions.anonymous]]
  - use when the func wouldn't be used anywhere else
  - presumably programmers occasionally convert anonymous functions into named functions
- [[t.cs.programming.functions.arrow]]
  - [[p.alsoKnownAs]] fat arrow functions
  - replace the word `function`
  - Compared with ordinary functions (declared with the function keyword): [[p.hasSource]] https://javascript.plainenglish.io/3-scenarios-where-you-shouldnt-use-arrow-functions-862388acd05d
    - An arrow function doesn’t have its own this value
    - It doesn’t have the arguments object.
    - It doesn’t have the `construct` internal slot. 
- [[t.cs.programming.loops]]
  - The for and forEach() loops both let you loop over the array's items, but the difference between them is that the for loop lets you exit if a certain condition is fulfilled
  - `numbers.forEach((number, index) => console.log(`Number ${number} ${index}`));`
- [[t.cs.programming.arrays]]
  - `find()`
    - e.g. `iceCreamFlavors.find(flavor => flavor === "Chocolate") // "Chocolate"`
    -  runs the function that you provided as input for each item. If the operation finds the searched-for element, it returns the element. If it doesn't find the element, it returns undefined.
 -  `filter()`
    -  e.g. `iceCreamFlavors.filter(flavor => flavor.type === "Chocolate")`
 -  `map()` (a projection)
    -  "The map() method creates a new array with the results of calling a provided function on every element in this array."
 -  `reduce()`
    -  reduces a long list of items into a single item
