---
id: xlkx8qi32gtkty8catja0jt
title: Discriminated Union
desc: 'allows you to model complex data types that can take on different shapes, explicitly defining which types can be assigned to a variable'
updated: 1732963054220
created: 1732962705455
---

- aka: tagged union or algebraic data type

## Examples

### Weave

```typescript
export type Inclusion =
  | {
    type: "git";
    name?: string;
    url: string;
    options?: GitOptions;
    order?: number;
  }
  | {
    type: "web";
    name?: string;
    url: string;
    options?: HttpOptions;
    order?: number;
  }
  | {
    type: "local";
    name?: string;
    url: string;
    options?: LocalOptions;
    order?: number;
  };
```
