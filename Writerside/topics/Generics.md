# Generics
Generics allow you to define a placeholder type that can be specified when the construct(eg function, class etc) 
is used, making the code more flexible and type-safe.

Consider the code below:

```Typescript
class DataStore {
  private data: number[] = [];

  addItem(item: number): void {
    this.data.push(item);
  }

  getItem(idx: number): number | null {
    if (idx < 0 || idx >= this.data.length) return null;
    return this.data[idx];
  }

  getAllItems(): number[] {
    return this.data;
  }
}
```
The code above is a 'stupid simple' implementation for a DataStore class that only stores numbers.

What if we wanted to now store strings or even booleans? We would have to copy the entire class
and maybe start changing the data types. But this is not really what we would want to do, and it doesn't
make sense when the only thing we want to change in our class is the type that we are using.

We need a way to variably be able to pass in a type and use a different type based on the instance of the class
that we need.

This is where generics come in.

In TypeScript, generics are a way to create reusable components that can work with different data types. Generics allow 
you to define a placeholder type that can be specified when the component is used, making the code more flexible and 
type-safe.

A generic is defined by placing a type parameter in angle brackets ```<T>``` after the function, class, or interface name. 
T is a common placeholder name, but you can use any identifier.

```Typescript
class DataStore<T> {
  private data: T[] = [];

  addItem(item: T): void {
    this.data.push(item);
  }

  getItem(idx: number): T | null {
    if (idx < 0 || idx >= this.data.length) return null;
    return this.data[idx];
  }

  getAllItems(): T[] {
    return this.data;
  }
}

const names = new DataStore<string>();
names.addItem("john");
names.addItem("june");
console.log(names.getAllItems());

const numbers = new DataStore<number>();
numbers.addItem(1);
numbers.addItem(2);
console.log(numbers.getAllItems());

interface User {
  name: string;
  age: number;
}

const users = new DataStore<User>();
users.addItem({ name: "John", age: 35 });
users.addItem({ name: "Smith", age: 43 });
console.log(users.getAllItems());
```

Generics allow us to have more flexibl functions, methods, classes etc that can accept different data types.
