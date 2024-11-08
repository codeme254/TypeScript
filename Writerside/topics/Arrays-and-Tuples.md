# Arrays and Tuples

## Arrays
An array is an ordered collection of elements stored in contiguous memory locations.

In typescript, when creating array, we can define what type of data will be stored in that array.

We can explicitly type arrays as shown below:

```Typescript
// an array of strings
const users: string[] = ["John", "Jane", "Smith"];
// an array of numbers
const scores: number[] = [25, 22, 20];
// an array of booleans
const isAdult: boolean[] = [true, false, true];
```

### Nested arrays
We can also have nested arrays:
```Typescript
const users: string[][] = [["jack"], ["jane", "john"], ["Jude", "Smith", "doe"]];
```

## Tuples
In TypeScript, a tuple is a specific type of array that has a fixed number of elements, where each element
has a defined type.

It is a fixed length array that has defined values for each position in the array.

```Typescript
// example 1: coordinates
const coordinate: [number, number] = [25.4, 36.8];
// example 2: user details
const userDetails: [string, number, boolean] = ["Alice", 25, true];
```

These two data structures can be combined to come up with a more complex yet useful data structure.

For example, an array of tuples:

```Typescript
const coordinates: [number, number][] = [
    [56.38, 45.5],
    [44.61, 98.491]
]
```