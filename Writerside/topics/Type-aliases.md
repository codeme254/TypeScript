# Type aliases

Type aliases allow you to create custom names for complex types, making your code more readable and maintainable.

Consider the function below:

```Typescript
function processCoordinates(
  p1: [number, number],
  p2: [number, number],
): [number, number] {
  return [p1[0], p2[1]];
}
```
As of now, we are repeating ```[number, number]``` multiple times, we can create an alias for it as shown:

```Typescript
type Coordinate = [number, number];

function processCoordinates(p1: Coordinate, p2: Coordinate): Coordinate {
  return [p1[0], p2[1]];
}
```