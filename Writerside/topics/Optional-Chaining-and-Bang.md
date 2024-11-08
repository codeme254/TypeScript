# Optional Chaining and Bang

**Question mark** and **Exclamation mark** operators allow us to check and deal with undefined values in Typescript.

**The code below will throw an error**
```Typescript
const myArr = [{ name: "John" }, { name: "June" }, { name: "Jack" }];
const username = myArr.pop().name;
```
**Explanation**:
Calling ```myArr.pop()``` is going to get the last element of the array from which we want to access
the name field, the problem comes in that, the call ```myArr.pop()``` might return an undefined value and that will
mean that we will be trying to access ```name``` from undefined.

To fix this, we need to check first whether ```myArr.pop()``` retuns a valid object first, only then do we try to access
the name property. We do this by the help of the ```?``` operator which will first of all check whehter ```myArr.pop()```
has returned a valid object as shown below:

```Typescript
const myArr = [{ name: "John" }, { name: "June" }, { name: "Jack" }];
const username = myArr.pop()?.name
```

## exclamation opearotr
This operator tells the compiler to avoid the possibility of a variable being undefined.