# Classes and Abstract Classes

## Classes
In JavaScript (and other object-oriented programming languages), a class is a blueprint for creating objects 
with shared properties and methods.

It serves as a template that allows you to create multiple instances (objects) with the same structure and behavior.

Below is a simple class in TypeScript:

```Typescript
class Person {
  name: string;

  constructor(name: string) {
    this.name = name;
  }

  greet(): void {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const john = new Person("John");
john.greet();
```

## Access modifiers
In object-oriented programming, access modifiers are keywords that set the accessibility (visibility) of classes, 
methods, and properties.

They control whether certain elements of a class can be accessed from outside the class or from within other classes, 
enforcing encapsulation and protecting data integrity.

JavaScript traditionally doesn't have access modifiers like other languages.

TypeScript however supports access modifiers.

The three main access modifiers are **public**, **private**, **protected**.

### private
When we mark a property or method as private, it can only be accessed within the class where it is defined.
This restricts direct access from outside the class, promoting encapsulation and safeguarding the data from unintended
modifications.

```Typescript
class Person {
  private name: string;

  constructor(name: string) {
    this.name = name;
  }

  greet(): void {
    console.log(`Hello, my name is ${this.name}`);
  }

  private sayGoodbye(): void {
    console.log(`Goodbye, this has been ${this.name}`);
  }
}

const john = new Person("John");
// THIS WILL NOT WORK
console.log(john.name);
// THIS WILL NOT WORK AS WELL
john.sayGoodbye()
```

### protected
A modifier that allows a property or method to be accessed within its own class and subclasses, but not from outside.

When you mark a property or a method as protected, it can only be accessed within the class or within the classes that
inherit from it but not outside.

```Typescript
class Person {
  protected name: string;

  constructor(name: string) {
    this.name = name;
  }

  greet(): void {
    console.log(`Hello, my name is ${this.name}`);
  }
}

class Social extends Person {
  sayGoodBye(): void {
    console.log(`Goodbye, this has been ${this.name}`);
  }
}

const s = new Social("Alice");
s.sayGoodBye();
```

### public
Public is the default access modifier, which means the property can be accessed from anywhere.

```Typescript
class Person {
  name: string;

  constructor(name: string) {
    this.name = name;
  }

  greet(): void {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const john = new Person("John");
john.greet();
```

## Abstract class
Refers to a restricted class that cannot be used to create objects and designed to be specifically used as a base class.

You cannot create an instance of an abstract class, you can extend it, override functionality, but you 
can't instantiate it.

```Typescript
abstract class Animal {
  // all classes inheriting from this abstract
  // class must implement the method below
  abstract makeSound(sound: string): void;

  move(): void {
    console.log("Moving along...");
  }
}

class Dog extends Animal {
  makeSound(sound: string): void {
    console.log(sound);
  }
}
const d = new Dog();
d.makeSound("woof woof");
d.move();

class Cat extends Animal {
  makeSound(sound: string): void {
    console.log(`Cats are cute animals`);
    console.log(`Their sound can communicate different things`);
    console.log(`But primarily, a cat ${sound}`);
  }
}
const c = new Cat();
c.makeSound("meows");
```