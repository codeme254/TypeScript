# Advanced Function Types

## Rest parameters

Rest parameters in JavaScript allow functions to accept an indefinite number of arguments as an array.

This is helpful when you don't know in advance how many arguments will be passed into the function, or when you want to 
handle multiple arguments flexibly.

```Typescript
function sum(...numbers: number[]) {
  let total: number = 0;
  for (let i = 0; i < numbers.length; i++) {
    total += numbers[i];
  }
  console.log(total);
}

sum(4, 5);
sum(5, 12, 12, 90);
sum(9);
```

```Typescript
function greetPeople(...names: string[]) {
  for (let i = 0; i < names.length; i++) {
    console.log(`Hello ${names[i]}`);
  }
}

greetPeople("Jack", "Smith")
greetPeople("John", "Bill", "Jane", "Doe")
greetPeople("Trump")
```

## Overloaded functions
An overloaded function is a function that has different call signatures and can accept different types.

Assuming we want a function that can take in either an array or a string and return a number, we could decide
to use a union type as shown below:

```Typescript
function getLength(param: string | string[]): number {
  if (typeof param === 'string') return param.length;
  if (Array.isArray(param)) return param.length;
  return 0
}

console.log(getLength("John Doe"))
console.log(getLength(["John", "Doe", "Jane", "Doe"]))
```

We can also use overloaded functions as shown below, we start by providing the functions signature
and then go ahead to provide their implementation:

```Typescript
function getLength(name: string): number;
function getLength(names: string[]): number;
// implementation of the two above functions
function getLength(param: unknown): number {
  if (typeof param === "string") return param.length;
  if (Array.isArray(param)) return param.length;
  return 0;
}

console.log(getLength("John Doe"));
console.log(getLength(["John", "Doe", "Jane", "Doe"]));
```