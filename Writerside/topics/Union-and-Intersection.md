# Union and Intersection
Unions and Intersection operators allow us to combine multiple types together to create more complex types.

Union operator is denoted by ```|```.

Intersection operator is dentoed by ```&```.

## Union type
A union type in TypeScript allows a variable to hold more than one type, providing flexibility while maintaining type 
safety.

You define a union type by using the | symbol between types.

```Typescript
type StringOrNumberOrBoolean = string | number | boolean;

const var1: StringOrNumberOrBoolean = "some value"; // valid
const var2: StringOrNumberOrBoolean = 45; //valid
let var3: StringOrNumberOrBoolean = true; //valid
var3 = "something else"; // valid
```

## Intersection type
The intersection operator in TypeScript, represented by ```&```, combines multiple types into one. 

An intersection type requires a value to have all the properties of each type in the intersection, 
effectively merging them.

```Typescript
interface Person {
  firstName: string;
  lastName: string;
}

interface PersonDetails {
  location: string;
  email: string;
  phoneNumber: string;
}

type Contact = Person & PersonDetails;

const contact: Contact = {
  firstName: "John",
  lastName: "Doe",
  location: "3rd Street",
  email: "johndoe@gmail.com",
  phoneNumber: "+123321456",
};

console.log(contact);
```