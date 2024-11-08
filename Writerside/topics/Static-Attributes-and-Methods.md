# Static Attributes and Methods

Static attributes are variables that are associated with the class rather than the instance of a class.

Static methods are methods that are associated with the class rather than an instance of the method.

They are usually defined using the ```static``` keyword.

```Typescript
var Dog = /** @class */ (function () {
  function Dog(name) {
    this.name = name;
    Dog.count++;
  }
  Dog.count = 0;
  return Dog;
})();
var j = new Dog("Jimmy");
var s = new Dog("Scooby");
console.log(Dog.count); // 2
```