# Utility types

Utility types are built-in types that enable you to transform and manipulate existing types in various ways.

These utility types are:

## Partial<T>
Partial utility type takes an exiting type and makes all it's properties optional.

```Typescript
interface User {
  name: string;
  age: number;
  location: string;
}

const alice: Partial<User> = { name: "Alice" };
console.log(alice);
```

## Required<T>
Required utility type makes all the properties of a type to be required ensuring that they must be provided even if they
had been marked as optional.

```Typescript
interface User {
  name: string;
  age?: number;
  location?: string;
  emailAddress?: string;
}

const alice: Required<User> = {
  name: "Alice",
  age: 25,
  location: "3rd Street",
  emailAddress: "alice@gmail.com",
};

console.log(alice);
```

## Readonly<T>
Creates a type where all properties are read only meaning they cannot be reassigned once created.

```Typescript
interface User {
  name: string;
}

const alice: Readonly<User> = { name: "Alice" };

alice.name = "Jane" // THIS WILL NOT WORK
```

## Record<K, T>
Constructs an object type with keys K and values of type T.

It is used to specify the type for keys ad values.

Often used to create maps or dictionaries with specific types for keys and values.

```Typescript
type Role = "admin" | "user" | "guest";
type Permission = Record<Role, string>;
// now key can either be admin, user or guest

const permissions: Permission = {
  admin: "Write, Read, Delete",
  user: "Read, Write",
  guest: "Read",
};

console.log(permissions);
```

## Pick<T, K>
Creates a new type by selecting a subset of properties K from type T.

Useful for extracting specific properties from a type.

```Typescript
interface User {
  name: string;
  emailAddress: string;
  age: string;
  location: string;
}

type Student = Pick<User, "name" | "emailAddress">;

const alice: Student = { name: "Alice", emailAddress: "alice@gmail.com" };
console.log(alice);
```

## Omit<T, K>
Creates a new type by omitting specific properties K from type T.

Helpful when you want most properties except a few.

```Typescript
interface User {
  name: string;
  age: number;
  course: string;
  emailAddress: string;
  location: string;
}

type Student = Omit<User, "emailAddress" | "location">;

const alice: Student = { name: "Alice", age: 25, course: "computer science" };
console.log(alice);
```

