# Implicit vs Explicit typing

In TypeScript, implicit and explicit typing refer to how variable types are assigned.

## Implicit typing
With implicit typing, TypeScript infers the type of a variable based on the initial assigned value.

You don’t need to specify the type explicitly; TypeScript determines it automatically.

```Typescript
let myVariable = "john";
// this will not work
myVariable = 25;
```

Here, ```myVariable``` is implicitly typed as a string because the initially assigned value is a string, we
didn't have to specify the data type, any attempt to assign a value with a different data type to this
variable will not work as specified in the snippet above.

## Explicit typing
With explicit typing, you specify the type of the variable directly.

This can help make your code more readable.

```Typescript
let myVariable: string = "john";
```