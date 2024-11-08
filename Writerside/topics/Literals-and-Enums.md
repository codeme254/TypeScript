# Literals and Enums

## Literals
In TypeScript, a literal represents a specific, exact value rather than a general type.

Literals allow you to restrict a variable to only one specific value or a set of predefined values.

This is useful for defining constants or limiting a variable’s value to a known set of options.

```Typescript
let direction: "north" | "south" | "east" | "west";
// this will work
direction = "north";
// this will work
direction = "east";
/////////////////////////
// THIS WILL NOT WORK///
///////////////////////
direction = "up";
```

## Enums
Enums stand for enumeration.

They enable developers to establish a collection of named constants each linked with an integer value.

We can have **numeric enums** and **string enums**.

### numeric enum
```Typescript
enum PizzaSize {
    Small, // corresponds to 0
    Medium, // corresponds to 1
    Large, // corresponds to 2
    ExtraLarge // corresponds to 3
}

let orderedPizzaSize: PizzaSize = 0;

if (orderedPizzaSize === PizzaSize.Small) {
    console.log(`Pay $5`);
}
```
The above enum is a numeric enum, the first element automatically corresponds to zero and the rest 
of the elements automatically increment by 1, we can change the starting point as shown:

```Typescript
enum PizzaSize {
    Small = 100,
    Medium,
    Large,
    ExtraLarge
}

console.log(PizzaSize.Small); // 100
console.log(PizzaSize.Medium); // 101
console.log(PizzaSize.Large); // 102
console.log(PizzaSize.ExtraLarge); // 103
```

We can also set completely custom integer values

```Typescript
enum PizzaSize {
    Small = 100,
    Medium = 200,
    Large = 300,
    ExtraLarge = 400
}

console.log(PizzaSize.Small); // 100
console.log(PizzaSize.Medium); // 200
console.log(PizzaSize.Large); // 300
console.log(PizzaSize.ExtraLarge); // 400
```

### string enum
```Typescript
enum Direction {
    Up = "Up",
    Down = "Down",
    Right = "Right",
    Left = "Left"
}

console.log(Direction.Right); // Right
```