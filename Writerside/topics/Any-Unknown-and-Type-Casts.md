# Any, Unknown and Type Casts

## any type
any type allows for flexible typing but sacrifices type safety as it lacks compile-time type checking.

What this means is that x can hold variable of any data type.

```Typescript
let myVariable: any = 5;
myVariable = "john doe";
myVariable = true;
myVariable = [1, 5, 1, 2, 9];
```

## unknown
The unknown type is a type-safe counterpart to the 'any' type.

It provides a powerful way to handle values of uncertain type while maintaining type safety.

With the unknown type, you will have to first assert what the type is before you start performing
an operation.

```Typescript
let myVar: unknown = 1;

// Performing type assertions
if (typeof myVar === "number") {
    console.log(myVar+2)
} else if (typeof myVar === "string") {
    console.log(myVar.length);
}
```

## type casting
Type casting allows you to tell the compiler to treat a value as a specific type.

It’s useful when you know more about the type of a value than TypeScript can infer on its own, like when dealing 
with DOM elements or data from APIs.

For example, casting to a number:

```Typescript
let myVar: unknown = 25;
const result = (myVar as number) + 25;
console.log(result);
```

Casting to a string:
```Typescript
let myVar: unknown = 25;
const result = (myVar as string) + "done";
console.log(result);
```