# Interfaces

Interfaces is a programming structure/syntax that allows the computer to enforce certain properties
on an object or a class.

Interfaces allow us to view objects as a specific type.

```Typescript
interface Person {
  firstName: string;
  lastName: string;
  age: number;
  emailAddress: string;
}

const person: Person = {
  firstName: "John",
  lastName: "Doe",
  age: 25,
  emailAddress: "johndoe@gmail.com",
};

console.log(person.firstName);
console.log(person.lastName);
```

If we want to specify optional properties, we use the question mark symbol ```?``` as shown:
```Typescript
interface Person {
  firstName: string;
  lastName: string;
  age?: number;
  emailAddress: string;
}

const person: Person = {
  firstName: "John",
  lastName: "Doe",
  emailAddress: "johndoe@gmail.com",
};

console.log(person.firstName);
console.log(person.lastName);
```

We can also have methods/functions within interfaces as shown:

```Typescript
interface Person {
  firstName: string;
  lastName: string;
  age?: number;
  emailAddress: string;
  // function that returns nothing
  greet: () => void;
}

const person: Person = {
  firstName: "John",
  lastName: "Doe",
  emailAddress: "johndoe@gmail.com",
  greet: function () {
    console.log("hello");
  },
};
person.greet();
```

## Extending interfaces
We can also 'copy' all the properties of one interface into another.

Assuming we want to create a new interface that contains all the properties of the Person interface above
but with only one or two properties added, the solution can be as simple as shown below:

```Typescript
interface Person {
  firstName: string;
  lastName: string;
  age?: number;
  emailAddress: string;
  // function that returns nothing
  greet?: () => void;
}

interface Employee extends Person {
  employeeId: string;
  department: string;
}

const john: Employee = {
  firstName: "john",
  lastName: "doe",
  emailAddress: "john@gmail.com",
  employeeId: "emp001-2002",
  department: "engineering",
};
console.log(john.department);
console.log(john.firstName);
```