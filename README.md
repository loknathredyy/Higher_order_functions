# HIGHER ORDER FUNCTIONS
In Javascript, functions can be assigned to variables in the same way that strings or arrays can. They can be passed into other functions as parameters or returned from them as well. A **higher-order function** is a function that accepts functions as parameters and/or returns a function.

## Assigning Functions to Variables
* We can assign functions to variables in JavaScript.

Example:

```
const square = function(x) {
  return x * x;
}// prints 25
square(5);
```
* We can also pass them around another variables.

Example:
```
const foo = square;

// prints 36
foo(6);
```
## Passing Functions as Parameters
* We can pass functions as parameters to other functions.

Example:
```
function formalGreeting() {
  console.log("How are you?");
}function casualGreeting() {
  console.log("What's up?");
}function greet(type, greetFormal, greetCasual) {
  if(type === 'formal') {
    greetFormal();
  } else if(type === 'casual') {
    greetCasual();
  }
}// prints 'What's up?'
greet('casual', formalGreeting, casualGreeting);
```
**For Example:**
 * Array.prototype.map, Array.prototype.filter and Array.prototype.reduce are some of the Higher-Order functions built into the language.

## Array.prototype.map

* The map() method creates a new array by calling the callback function provided as an argument on every element in the input array.
* The callback function passed to the map() method accepts 3 arguments: element, index, and array.

### Without Higher-order function
```
const arr1 = [1, 2, 3];
const arr2 = [];
for(let i = 0; i < arr1.length; i++) {
  arr2.push(arr1[i] * 2);
}// prints [ 2, 4, 6 ]
console.log(arr2);
```
### With Higher-order function map
```
const arr1 = [1, 2, 3];
const arr2 = arr1.map(function(item) {
  return item * 2;
});console.log(arr2);
```
* We can make this even shorter using the arrow function syntax:
```
const arr1 = [1, 2, 3];
const arr2 = arr1.map(item => item * 2);
console.log(arr2);
```
## Array.prototype.filter
* The filter() method creates a new array with all elements that pass the test provided by the callback function.
* The callback function passed to the filter() method accepts 3 arguments: element, index, and array.
  
### Without Higher-order function
```
const persons = [
  { name: 'Peter', age: 16 },
  { name: 'Mark', age: 18 },
  { name: 'John', age: 27 },
  { name: 'Jane', age: 14 },
  { name: 'Tony', age: 24},
];

const fullAge = [];
for(let i = 0; i < persons.length; i++) {
  if(persons[i].age >= 18) {
    fullAge.push(persons[i]);
  }
}

console.log(fullAge);
```

### With Higher-order function filter
```
const persons = [
  { name: 'Peter', age: 16 },
  { name: 'Mark', age: 18 },
  { name: 'John', age: 27 },
  { name: 'Jane', age: 14 },
  { name: 'Tony', age: 24},
];

const fullAge = persons.filter(person => person.age >= 18);

console.log(fullAge);
```
## Array.prototype.reduce
* The reduce method executes the callback function on each member of the calling array which results in a single output value. 
* The reduce method accepts two parameters: 
    1. The reducer function (callback). 
    2. An optional initialValue.

* The reducer function (callback) accepts four parameters: accumulator, currentValue, currentIndex, sourceArray.

### Without Higher-order function
```
const arr = [5, 7, 1, 8, 4];
let sum = 0;
for(let i = 0; i < arr.length; i++) {
  sum = sum + arr[i];
}

// prints 25
console.log(sum);
```

### With Higher-order function reduce
```
const arr = [5, 7, 1, 8, 4];
const sum = arr.reduce(function(accumulator,currentValue) {
  return accumulator + currentValue;
});

// prints 25
console.log(sum);
```
* We can also provide an initial value to this function:

```
const arr = [5, 7, 1, 8, 4];
const sum = arr.reduce(function(accumulator, currentValue) {
  return accumulator + currentValue;
}, 10);

// prints 35
console.log(sum);
```

## References:

* [bitsrc.io](https://blog.bitsrc.io/understanding-higher-order-functions-in-javascript-75461803bad)
* [codecademy](https://www.codecademy.com/learn/game-dev-learn-javascript-higher-order-functions-and-iterators/modules/game-dev-learn-javascript-iterators/cheatsheet)