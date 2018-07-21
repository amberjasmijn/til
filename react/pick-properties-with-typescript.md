# Pick properties with TypeScript
Apparently it is possible to pick a set of properties with `Pick` in TypeScript. 

```
/**
 * From T pick a set of properties K
 */
type Pick<T, K extends keyof T> = {
    [P in K]: T[P];
};
```

This can come in handy when you need a selected set of properties, for example when mapping your state to props in React and Redux in TypeScript.


