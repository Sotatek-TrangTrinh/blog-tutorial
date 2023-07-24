<h1 align="center">JAVASCRIPT</h1>

### NULLISH COALESCING OPERATOR (??)

```c
if (leftExpr === null || leftExpr === undefined)
  return rightExpr
else
  return leftExpr
```

### LOGICAL OR (||)

```c
if (leftExpr is falsy value)
  return rightExpr
else
  return leftExpr
```

### FALSY VALUE

- null
- undefined
- false
- NaN
- 0
- -0
- 0n (BigInt)
- "", '', ``

### CALLBACK

A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.

The above example is synchronous callback

```c
function greeting(name) {
  alert(`Hello, ${name}`);
}

function processUserInput(callback) {
  const name = prompt("Please enter your name.");
  callback(name);
}

processUserInput(greeting);
```

The above example is synchronous callback:

```c
const addButton = document.querySelector("#add")
addButton.addEventListener("click", () => {
  console.log("You clicked #addButton")
})
```

### DATE AND TIME

```c
new Date() // Tue Jun 06 2023 10:34:35 GMT+0700 (Indochina Time) {}
+ new Date() // 1686022389939
```

### ARRAY

- spread syntax
  s

```c
arr = [2, 4, 8, 6, 0];
max = Math.max(...arr);

str = "hello";
chars = [...str];
```

- slice

```c
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
fruits.slice();  //["Banana", "Orange", "Lemon", "Apple", "Mango"]
fruits.slice(3);  //["Apple", "Mango"]
fruits.slice(1, 4);  //["Orange", "Lemon", "Apple",]
```

- length

```c
const numbers = [1, 2, 3, 4, 5];

if (numbers.length > 3) {
  numbers.length = 3; ///[1, 2, 3]
}
```
