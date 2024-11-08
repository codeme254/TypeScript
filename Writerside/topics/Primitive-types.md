# Primitive types

Primitive types are the basic data types that represent simple values and are immutable.

## numbers
Numeric values, could be positive numbers, negative numbers, 0, Infinity, -Infinity and floating point 
numbers.

Use the ```number``` keyword to define number data types in TypeScript:

```Typescript
const myInteger: number = 5;
const negative: number = -48;
const myFloat: number = 56.835;
const zero: number = 0;
const infinity: number = Infinity;
const negativeInfinity: number = -Infinity;
```

## strings
A string is a collection of characters enclosed within double, single quotes or backticks.

Use ```string``` keyword to define a string data type in typescript.

```Typescript
const firstName: string = "John";
const lastName: string = 'doe';
const emailAddress: string = `johdoe@gmail.com`;
const fullName: string = `${firstName} ${lastName}`;
```

## booleans
booleans can either be true or false.

Use ```boolean``` keyword to define a boolean data type in typescript.

```Typescript
const isMale: boolean = true;
const isFemale: boolean = false;
```

## null
null is used when we want to explicitly define something that is empty or non-existent.

null variables automatically get ```any``` data type which means they can hold values of any data type.

```Typescript
let result = null;
result = true;
result = "john";
result = 25;
```

A very simple fix for this would be to use the ```null``` data type as shown and the variable will never 
accept any other data type:

```Typescript
let result:null = null;
```

## undefined
undefined is used as a placeholder to mean that a variable has been declared but has not yet been assigned
a value but will have a value in the near future.

## void type
```void``` type is used when we are returning nothing from a function.

## never type
```never``` type is used when we have a function that does not return a value.

