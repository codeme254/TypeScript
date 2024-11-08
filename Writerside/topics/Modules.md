# Modules

A module is just a typescript file.

In a module, we can either import code or export code.

## Named export
```Typescript
export function funcName() {}
```
or
```Typescript
function fun1() {}

function func2() {}

export {func1, func2}
```

```util.ts```

```Typescript
export function add(num1: number, num2: number): number {
  return num1 + num2;
}
```

```app.ts```

```Typescript
import { add } from "./util";

console.log(add(5, 5));
```

## Default export
```util.ts```
```Typescript
function add(num1: number, num2: number): number {
  return num1 + num2;
}

export default add;
```

```app.ts```
```Typescript
import add from "./util";

console.log(add(5, 5));
```