# Type Guards

Type guards are a way of checking the type of a value at runtime and narrowing its type in a conditional block.

For example, ```typeof``` that we have been using is a type guard.

The main idea is to use a type guard to provide something known as ```type narrowing```.

**typeof**, **instanceof**, **in**, **is** keywords/operators help in achieving type guarding.

**Type narrowing** allows us to take a type that is more general and we can narrow it to a more concrete type.

## using typeof for primitive type guards
```Typescript
type StringOrNumber = string | number;

function addTo1(value: StringOrNumber): StringOrNumber {
  if (typeof value === "string") return value + "1";
  return value + 1;
}
```

## using instanceof for objects type guard
```Typescript
class Dog {
  firstName: string;
  lastName: string;

  constructor(firstName: string, lastName: string) {
    this.firstName = firstName;
    this.lastName = lastName;
  }
}

class Cat {
  firstName: string;

  constructor(firstName: string) {
    this.firstName = firstName;
  }
}

function getAnimalName(animal: Dog | Cat): void {
  if (animal instanceof Dog) {
    console.log(`Name: ${animal.firstName} ${animal.lastName}`);
  } else if (animal instanceof Cat) {
    console.log(`Name: ${animal.firstName}`);
  }
}

const scoob = new Dog("Scooby", "Doo");
getAnimalName(scoob);
```