# Classes and Interfaces

Classes can also implement interfaces.

Interfaces don't implement any functionality or behavior, this is their fundamental difference from abstract
classes, abstract classes can implement some methods.

```Typescript
interface Animal {
  speak(): void;
}

class Dog implements Animal {
  private name: string;
  private color: string;

  constructor(name: string, color: string) {
    this.name = name;
    this.color = color;
  }
  speak(): void {
    console.log(`Hello, I am ${this.name} and I am ${this.color}`);
  }

  run(): void {
    console.log(`Dog running`);
  }
}

const d = new Dog("Scoob", "White");
d.speak();
d.run();
```