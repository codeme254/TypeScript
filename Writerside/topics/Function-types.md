# Function types

## Typing parameters
```Typescript
function add (x: number, y: number) {
    return x + y;
}
```

## Specifying the type of the return value
```Typescript
function add (x: number, y: number): number {
    return x + y;
}
```

## Specifying 'either of the return types'
```Typescript
function add (x: number, y: number): number | string {
    return x + y;
}
```

## Marking a parameter as optional using ```?```
```Typescript
function add (x: number, y: number, z?: number): number | string {
    console.log(z)
    return x + y;
}
```

## Typing callback functions
Use an arrow function, the specify the parameters that the function is to accept, for the return of the
function, use the data type that the function is supposed to return.
```Typescript
function callFunc(
  callback: (f: string, l: string) => string,
  param1: string,
  param2: string,
) {}
```