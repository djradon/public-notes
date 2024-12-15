---
id: ivh9jd8nfbqs6x7hsn51e7g
title: Operator
desc: ''
updated: 1734153775818
created: 1734153524114
---

## Nullish Coalescing Operator (??)

This operator is used to provide a default value if the left-hand side is null or undefined. It is similar to the logical OR (||) operator, but with a narrower definition of falsy; it doesn't consider values like 0, false, or "" as needing to default.

## Logical AND (&&) Operator: 

This expression leverages the fact that the && operator returns the first falsy value encountered or the last operand if all are truthy.

&& is more commonly used in inline conditional logic when you do not need an alternative else case, as it is shorter for simply returning or doing something if the condition is truthy.

Evaluation of `${name && ${name}: || ""}${url}`:
If name is falsy (such as null, undefined, false, 0, "", or NaN), the whole expression evaluates to this falsy value
If name is truthy, the expression proceeds to evaluate and return ${name}: 