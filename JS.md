### **JavaScript Cheatsheet**

#### **1. Variables**

- **`let`**: Block-scoped, can be reassigned.
- **`const`**: Block-scoped, cannot be reassigned.
- **`var`**: Function-scoped, avoid using due to hoisting issues.

```javascript
let x = 5;
const y = 10;
var z = 15;
```

#### **2. Data Types**

- **Primitive**: `String`, `Number`, `Boolean`, `Null`, `Undefined`, `Symbol`, `BigInt`
- **Non-primitive**: `Object`, `Array`, `Function`

```javascript
let name = "John"; // String
let age = 30; // Number
let isStudent = true; // Boolean
let person = { name: "John", age: 30 }; // Object
let colors = ["red", "green", "blue"]; // Array
```

#### **3. Functions**

- **Function Declaration**:

```javascript
function greet(name) {
  return "Hello, " + name;
}
```

- **Function Expression**:

```javascript
const greet = function (name) {
  return "Hello, " + name;
};
```

- **Arrow Functions**:

```javascript
const greet = (name) => `Hello, ${name}`;
```

#### **4. Loops**

- **`for` Loop**:

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

- **`forEach` Loop (Array)**:

```javascript
colors.forEach((color) => console.log(color));
```

- **`while` Loop**:

```javascript
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```

#### **5. Conditional Statements**

- **`if` Statement**:

```javascript
if (age > 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}
```

- **`switch` Statement**:

```javascript
switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  default:
    console.log("Unknown day");
}
```

#### **6. Arrays**

- **Create an Array**:

```javascript
let fruits = ["Apple", "Banana", "Cherry"];
```

- **Array Methods**:
  - `push()`: Add item to end.
  - `pop()`: Remove item from end.
  - `shift()`: Remove item from start.
  - `unshift()`: Add item to start.
  - `map()`: Create new array by applying a function to each item.

```javascript
let doubled = [1, 2, 3].map((num) => num * 2); // [2, 4, 6]
```

#### **7. Objects**

- **Create an Object**:

```javascript
let car = { brand: "Toyota", model: "Corolla", year: 2020 };
```

- **Access Object Properties**:

```javascript
console.log(car.brand); // Dot notation
console.log(car["model"]); // Bracket notation
```

#### **8. Object Methods**

- **Define a method inside an object**:

```javascript
let person = {
  name: "John",
  greet() {
    console.log(`Hello, ${this.name}`);
  },
};
person.greet(); // Output: Hello, John
```

#### **9. Destructuring**

- **Arrays**:

```javascript
const [a, b] = [10, 20];
```

- **Objects**:

```javascript
const { brand, model } = car;
```

#### **10. Spread & Rest Operators**

- **Spread (`...`)**: Expands arrays or objects.

```javascript
let arr1 = [1, 2];
let arr2 = [...arr1, 3, 4]; // [1, 2, 3, 4]
```

- **Rest (`...`)**: Collects remaining elements.

```javascript
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}
```

#### **11. Promises & Async/Await**

- **Promise**:

```javascript
let promise = new Promise((resolve, reject) => {
  // Asynchronous work
  resolve("Success!");
});
promise
  .then((result) => console.log(result))
  .catch((error) => console.log(error));
```

- **Async/Await**:

```javascript
async function fetchData() {
  let response = await fetch("https://api.example.com/data");
  let data = await response.json();
  console.log(data);
}
```

#### **12. Template Literals**

- Use backticks to create strings with embedded expressions:

```javascript
let greeting = `Hello, ${name}! You are ${age} years old.`;
```

#### **13. DOM Manipulation**

- **Select Element**:

```javascript
const element = document.getElementById("myElement");
```

- **Change Content**:

```javascript
element.textContent = "New Content";
```

- **Add Event Listener**:

```javascript
element.addEventListener("click", () => {
  console.log("Element clicked");
});
```

#### **14. JSON**

- **Parse JSON**:

```javascript
let jsonData = '{"name": "John", "age": 30}';
let obj = JSON.parse(jsonData);
```

- **Stringify Object**:

```javascript
let stringData = JSON.stringify(obj);
```

---
