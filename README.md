# Javascript Array Methods

This document contains all the basic array methods of JavaScript, their definitions, and usage examples.

# Array Methods

### concant()

It is used to concatenate two or more arrays. It returns a new array.

```jsx
const array1 = ["a", "b", "c"];
const array2 = ["d", "e", "f"];

const array3 = array1.concat(array2);

console.log(array3); // Array ["a", "b", "c", "d", "e", "f"]
```

### copyWithin()
It copies a section of an array to another array, overwriting it without changing the length of the copied array.

```jsx
const array1 = ["a", "b", "c", "d", "e"];

console.log(array1.copyWithin(0, 3, 4)); // Array ["d", "b", "c", "d", "e"]

console.log(array1.copyWithin(1, 3)); // Array ["d", "d", "e", "d", "e"]

```

### every()
It returns a boolean value depending on whether all elements in the array satisfy the specified condition.

```jsx
const array1 = [1, 30, 39, 29, 10, 13];
console.log(array1.every((eleman) => eleman !== 0)); //true

```

### filter()
It returns a new array containing copies of the elements in the given array that satisfy the specified conditions.

```jsx
const words = [
  "spray",
  "limit",
  "elite",
  "exuberant",
  "destruction",
  "present",
];

const result = words.filter((word) => word.length > 6);

console.log(result); // Array ["exuberant", "destruction", "present"]
```

### forEach()
This method is used to invoke a specified function for each element in an array.

```jsx
const array1 = ["a", "b", "c"];

array1.forEach((element) => console.log(element));

array1.forEach((element, index) => console.log(index + " : " + element));
```

### indexOf()

It returns the index number of the element in the array, or -1 if it is not found.

```jsx
const beasts = ["ant", "bison", "camel", "duck", "bison"];

console.log(beasts.indexOf("bison")); // 1

console.log(beasts.indexOf("bison", 2)); // 4

console.log(beasts.indexOf("giraffe")); // -1
```

### lastIndexOf()
It returns the last index of the searched element in the array. It is useful in arrays with multiple occurrences of the same element.

```jsx
const animals = ["Dodo", "Tiger", "Penguin", "Dodo"];

console.log(animals.lastIndexOf("Dodo")); // 3

console.log(animals.lastIndexOf("Tiger")); // 1
```

### map()

Its purpose is to iterate over each element in the array, performing a specific operation on each one to generate a new array.

```jsx
const array1 = [1, 4, 9, 16];

const array2 = array1.map((x) => x * 2);

console.log(array2); // Array [2, 8, 18, 32]
```

### reduce()
It is an array method used to loop through all elements in an array and obtain a result by concatenating them or summing them up.

```jsx
const array1 = [1, 2, 3, 4];

const initialValue = 0; // initial value

const sum = array1.reduce(
  (previousValue, currentValue) => previousValue + currentValue,
  initialValue
);

//return 0+1+2+3+4 = 10

```
We can assign any value we want as the initial value. If there is no previous value, it accepts the value of the first element in the array as the initial value. (here the first element is 1)

```jsx
const array1 = [1, 2, 3, 4];

const sum = array1.reduce((prev, current) => {
  return prev + current;
}, 2);

console.log(sum); // 2 + 1 + 2 + 3 + 4 = 12
```

### reduceRight()
It works the same as reduce, but it moves from the end to the beginning of the array.

```jsx
const array1 = [0, 1, 2, 3, 4];

let sum = array1.reduceRight((prev, current) => prev + " - " + current);

console.log(sum); // 4 - 3 - 2 - 1 - 0;
```

### reverse()
It reverses the elements of an array in reverse order based on their indices.

```jsx
const array1 = ["one", "two", "three"];

const reversed = array1.reverse();

console.log(reversed); // ["three", "two", "one"]

```

### slice()

It returns a copy of a portion of an array within a specified range of indexes. It does not modify the original array. The second parameter, which represents the end index, is not included in the slice; that is, slice[0,2] method returns the values with indexes 0 and 1.

```jsx
const animals = ["ant", "bison", "camel", "duck", "elephant"];

console.log(animals.slice(2)); // Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4)); // Array ["camel", "duck"]

console.log(animals.slice(1, 5)); // Array ["bison", "camel", "duck", "elephant"]

console.log(animals.slice(-2)); // Array ["duck", "elephant"]

console.log(animals.slice(2, -1)); // Array ["camel", "duck"]
```

### some()
It is used to return true if the specified condition is satisfied at least once in the array, otherwise it returns false.

```jsx
  [0, 1, 2, 3, 4].some((element) => element > 2) //return true
  [0, 1, 2, 3, 4].some((element) => element % 2 === 0) //return true
  [0, 1, 2, 3, 4].some((element) => element > 5); //return false

```

### sort()

It sorts the elements of the array in ascending order. However, since it sorts based on UTF-16 code unit values, it may not always display the expected results. It modifies the original array.

```jsx
const names = ["Mahrous", "Ali", "Taha", "Soha"];
names.sort();
console.log(names); // return ["Ali", "Mahrous", "Soha", "Taha"]
```

**IMPORTANT:** You can achieve the correct sorting by passing a comparison function when dealing with numbers.

```jsx
let numbers = [40, 100, 1, 5, 25, 10];
numbers.sort(function (a, b) {
  return a - b;
});

console.log(numbers); // [1, 5, 10, 25, 40, 100]
```

### splice()
It is an array method used to add, remove, or change elements in arrays. This method modifies the array and returns the modified elements as a new array.

```jsx
array.splice(start, deleteCount, item1, item2, ...);
```

Parametreler:
- **`start`**: The starting index in the array where changes will be made. Adding or removing operations start from this index.
- **`deleteCount`**: The number of elements to be deleted starting from the start index. If 0, no elements are deleted, only additions are made.
- **`item1, item2, ...`**: New elements to be added. These parameters are optional.

```jsx
let numbers = [10, 20, 30, 40, 50];
numbers.splice(2, 2);

console.log(numbers); // [10, 20, 50]
```
### entries()

This is a method of an array or an object that returns an array consisting of key-value pairs for each element in the array or object. It returns a new array.

```jsx
const fruits = ["apple", "banana", "orange"];

const entries = fruits.entries();

for (const entry of entries) {
  console.log(entry);
}
// [0, 'apple']
// [1, 'banana']
// [2, 'orange']
```

### fill()

It replaces the elements in an array with the given value and returns the modified array. It does not add more elements than the length of the array. The fill() function syntax is fill(value, start, end).

```jsx
const array1 = [1, 2, 3, 4];

console.log(array1.fill(0, 2, 4)); //  Array [1, 2, 0, 0]

console.log(array1.fill(5, 1)); // Array [1, 5, 5, 5]

console.log(array1.fill(6)); //Array [6, 6, 6, 6]
```

### find()

It returns the first element in the array that satisfies the given condition. If no element satisfies the condition, it returns the value undefined.

```jsx
const array1 = [5, 12, 8, 130, 44];

const found = array1.find((element) => element > 10);

console.log(found); // 12
```

### findIndex()
It returns the index number of the first element in the array that satisfies the given condition. If there is no element that satisfies the condition, it returns `-1`.

```jsx
const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber)); // 3
```

### findLast()
It returns the first element in the array, starting from the end and moving towards the beginning, that satisfies the given condition. If no such element is found, it returns `undefined`.

```jsx
const array1 = [5, 12, 50, 130, 44];

const found = array1.find((element) => element > 45);

console.log(found); // 130
```

### findLastIndex()
It returns the index number of the first element in the array, starting from the end and moving towards the beginning, that satisfies the given condition. If no such element is found, it returns `-1`.

```jsx
const array1 = [5, 12, 50, 130, 44];

const isLargeNumber = (element) => element > 45;

console.log(array1.findLastIndex(isLargeNumber)); // 3
```

### includes()

It checks if a specific value exists in an array and returns true or false.

```jsx
const pets = ["cat", "dog", "bat", 12];

console.log(pets.includes(12)); //true
console.log(pets.includes("a")); //false
console.log([0, 1, , 2].includes(undefined)); //true
```

### join()

It returns a new string by concatenating the elements of an array.

```jsx
const elements = ["Fire", "Air", "Water"];

console.log(elements.join()); // "Fire,Air,Water"
console.log(elements.join("")); // "FireAirWater"
console.log(elements.join("-")); // "Fire-Air-Water"
console.log([1, undefined, 3].join()); // '1,,3'
```

### keys()
It returns the index number for each element in the array. It's more useful when used with objects.

```jsx
const array1 = ["a", "b", , "c"];
const ite = Object.keys(array1);
console.log(ite); // ["0","1","3"]

```

### toLocaleString()
It returns the locale-sensitive string representation of a date.

```jsx
let date = new Date();

console.log(date); //return Tue Apr 30 2024 05:32:20 GMT+0300 (Eastern European Summer Time)
console.log(date.toLocaleString("tr-TR")); //return 30.04.2024 05:32:20
```

### pop()

This method removes the last element from the array and returns the removed element. It modifies the array.

```jsx
const myArray = [1, 2, 3, 4, 5];
myArray.pop();
console.log(myArray); // [1, 2, 3, 4]

const emptyArray = [];
console.log(emptyArray.pop()); // undefined
```

### shift()

This method removes the first element from the array and returns the removed element. It modifies the array

```jsx
const myArray = [1, 2, 3, 4, 5];

myArray.shift();
console.log(myArray); // [2, 3, 4, 5]
```

### push()
This method adds one or more elements to the end of the array. It modifies the array and returns its new length.

```jsx
const myArray = [1, 2, 3, 4];
myArray.push(5);
console.log(myArray); // [1, 2, 3, 4, 5]

const myArray = [1, 2, 3, 4];
const additionalItems = [5, 6];

myArray.push(...additionalItems);
console.log(myArray); // [1, 2, 3, 4, 5, 6]
```

### unshift()
This method adds new element(s) to the array, shifting existing elements to make space at the beginning of the array. It modifies the array.

```jsx
const myArray = [3, 4, 5];
myArray.unshift(1, 2); // [1, 2, 3, 4, 5]
```
