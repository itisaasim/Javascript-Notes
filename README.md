# JavaScript Notes

## Content:

### ✅ Phase 1: Core Basics (Foundational stuff)

1. **Variables (var, let, const)**
2. **Data Types**
3. **Operators**
4. **Control Flow (if, switch)**
5. **Loops (for, while, do...while)**
6. **Functions (declaration, expression, arrow)**
7. **Scope & Hoisting**
8. **Type Conversion & Coercion**
9. **Truthy/Falsy Values**
10. **Arrays & Objects (basic)**

---

### ✅ Phase 2: Intermediate Concepts

1. **Array Methods (map, filter, reduce, etc.)**
2. **Callback Functions**
3. **Closures**
4. **this Keyword**
5. **Object-Oriented JS (Prototypes, Inheritance)**
6. **ES6+ Features (Destructuring, Spread, etc.)**
7. **Error Handling**
8. **Timers (setTimeout, setInterval)**

---

### ✅ Phase 3: Advanced Concepts

1. **Promises & Async/Await**
2. **Event Loop & Call Stack**
3. **Functional Programming Principles**
4. **Modules (import/export)**
5. **Memory Management**
6. **Web APIs & DOM Events**
7. **Debouncing & Throttling**
8. **Design Patterns in JS**

---

## PHASE 1

## 1. Variables (`var`, `let`, `const`)

**🧠 Definition:**

Variables are containers for storing data values. In JavaScript, we can declare variables using `var`, `let`, or `const`.

---

**🧾 Syntax:**

```jsx
javascript
CopyEdit
var name = "Alice";
let age = 25;
const country = "India";

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
var city = "Bhopal";
let temperature = 30;
const isHot = true;

console.log(city);        // "Bhopal"
console.log(temperature); // 30
console.log(isHot);       // true

```

---

**✅ What to do with it:**

- Use `let` when the variable's value needs to change.
- Use `const` for values that should not change (constants).
- Use meaningful names (`userName`, `totalPrice`) to describe the data.
- Prefer `let` and `const` over `var` in modern JavaScript.

---

**❌ What not to do with it:**

- ❌ Don’t use `var` unless needed for legacy support (it’s function-scoped and hoists weirdly).
- ❌ Don’t redeclare a `let` or `const` variable in the same scope.
- ❌ Don’t assign a new value to a `const` variable (though objects declared with `const` can have their properties changed).

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS* (Scope & Closures) – Chapters 2 & 3
- 📘 *Eloquent JavaScript* – Chapter 2: Program Structure
- 🌐 javascript.info – “var, let and const”

## 2. Data Types

**🧠 Definition:**

JavaScript has **dynamic typing**, which means variables can hold values of any type without declaring it explicitly. There are two main categories of data types: **primitive** and **non-primitive (reference)**.

---

**🧾 Syntax:**

```jsx
javascript
CopyEdit
let name = "Alice";           // String
let age = 25;                 // Number
let isStudent = true;         // Boolean
let undefinedValue;           // Undefined
let emptyValue = null;        // Null
let uniqueId = Symbol("id");  // Symbol
let bigIntValue = 123n;       // BigInt

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
// Primitive types
let name = "John";       // String
let score = 95;          // Number
let isPassed = true;     // Boolean
let nothing = null;      // Null
let notDefined;          // Undefined
let symbolKey = Symbol(); // Symbol
let bigNumber = 9999999999999999n; // BigInt

// Reference types
let student = { name: "John", age: 22 }; // Object
let scores = [90, 80, 85];              // Array (also an object)
let greet = function() { return "Hi"; }; // Function (also an object)

```

---

**✅ What to do with it:**

- Use `typeof` to check the type of a value.
- Use `===` instead of `==` for strict comparisons (type + value).
- Use `null` intentionally to represent "no value".
- Remember arrays and functions are **objects**.

---

**❌ What not to do with it:**

- ❌ Don’t confuse `null` and `undefined` — `null` is intentional absence, `undefined` means not assigned.
- ❌ Don’t use `==` (loose equality) unless you understand type coercion.
- ❌ Don’t assume all objects are the same — arrays, dates, functions are all technically objects but behave differently.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Types & Grammar)* – Chapter 1: Types
- 📘 *Eloquent JavaScript* – Chapter 1: Values, Types, and Operators
- 🌐 javascript.info – “Data types”

## 3. Operators

**🧠 Definition:**

Operators in JavaScript are symbols or keywords that perform operations on values and variables. They are used to assign values, compare values, perform arithmetic operations, and more.

---

**🧾 Syntax Examples:**

```jsx
javascript
CopyEdit
let a = 10 + 5;     // Arithmetic (+)
let isEqual = a === 15;  // Comparison (===)
a += 1;             // Assignment (+=)
let isTrue = true && false; // Logical (&&)

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
let x = 5;
let y = 10;

console.log(x + y);      // 15 (Arithmetic)
console.log(x > y);      // false (Comparison)
x += 2;
console.log(x);          // 7 (Assignment)
console.log(true && false); // false (Logical)
console.log(!true);      // false (Logical NOT)

```

---

**🧮 Types of Operators:**

| Type | Operators | Example |
| --- | --- | --- |
| Arithmetic | +, -, *, /, %, ** | `5 + 2` → 7 |
| Assignment | =, +=, -=, *=, /= | `x += 1` |
| Comparison | ==, ===, !=, !==, >, < | `x === y` |
| Logical | &&, ||, ! | `true && false` |
| Unary | typeof, void, delete | `typeof 123` |
| Ternary | condition ? val1 : val2 | `isCool ? "😎" : "😐"` |

---

**✅ What to do with it:**

- Use `===` and `!==` for strict comparison (no type coercion).
- Understand precedence (e.g., multiplication happens before addition).
- Group expressions with parentheses for clarity.

---

**❌ What not to do with it:**

- ❌ Don’t use `==` unless you *really* understand type coercion rules.
- ❌ Don’t chain assignments without parentheses (`a = b = c = 10` can be confusing).
- ❌ Don’t assume `true && "hello"` will always return a boolean (it returns `"hello"`).

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Types & Grammar)* – Chapter 2: Values & Types
- 📘 *Eloquent JavaScript* – Chapter 2: Program Structure
- 🌐 javascript.info – “Operators”

---

## 4. Control Flow (`if`, `else`, `switch`)

**🧠 Definition:**

Control flow determines the order in which code is executed. JavaScript executes code from top to bottom, but **control flow statements** like `if`, `else`, and `switch` let you change the flow based on conditions.

---

**🧾 Syntax:**

```jsx
javascript
CopyEdit
if (condition) {
  // code block if true
} else {
  // code block if false
}

switch (expression) {
  case value1:
    // code block
    break;
  case value2:
    // code block
    break;
  default:
    // default code
}

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
let score = 85;

if (score >= 90) {
  console.log("A grade");
} else if (score >= 80) {
  console.log("B grade");
} else {
  console.log("C grade");
}
// Output: B grade

let fruit = "apple";

switch (fruit) {
  case "banana":
    console.log("Yellow fruit");
    break;
  case "apple":
    console.log("Red fruit");
    break;
  default:
    console.log("Unknown fruit");
}
// Output: Red fruit

```

---

**✅ What to do with it:**

- Use `if/else` for simple, readable conditionals.
- Use `switch` for multiple possible exact matches.
- Use `break` in each `switch` case to avoid "fallthrough".
- Group similar cases in `switch` if they have the same logic.

---

**❌ What not to do with it:**

- ❌ Don’t forget `break` in `switch` cases unless fallthrough is intended.
- ❌ Don’t use `switch` when conditions are complex (like ranges or multiple checks).
- ❌ Don’t over-nest `if` blocks — extract logic into functions for readability.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Scope & Closures)* – Chapter 2 (examples on flow)
- 📘 *Eloquent JavaScript* – Chapter 2: Program Structure
- 🌐 javascript.info – “Conditional branching: if, '?', switch”

---

## 5. Loops (`for`, `while`, `do...while`, `for...in`, `for...of`)

**🧠 Definition:**

Loops are used to execute a block of code repeatedly until a specified condition is met. JavaScript supports several types of loops, each with different use cases.

---

**🧾 Syntax:**

```jsx
javascript
CopyEdit
// for loop
for (let i = 0; i < 5; i++) {
  console.log(i);
}

// while loop
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}

// do...while loop
let j = 0;
do {
  console.log(j);
  j++;
} while (j < 5);

// for...in (used with objects)
const user = { name: "John", age: 30 };
for (let key in user) {
  console.log(key, user[key]);
}

// for...of (used with arrays, strings, etc.)
const arr = [10, 20, 30];
for (let num of arr) {
  console.log(num);
}

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
const fruits = ["apple", "banana", "cherry"];

// using for loop
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}

// using for...of
for (let fruit of fruits) {
  console.log(fruit);
}

// using for...in (not ideal for arrays, better for objects)
for (let index in fruits) {
  console.log(fruits[index]);
}

```

---

**✅ What to do with it:**

- Use `for...of` for clean iteration over arrays.
- Use `for...in` to loop over object keys.
- Use `break` to exit a loop early.
- Use `continue` to skip the current iteration.

---

**❌ What not to do with it:**

- ❌ Don’t use `for...in` for arrays — it iterates over keys, not values.
- ❌ Don’t forget to update loop variables — risk of infinite loops.
- ❌ Don’t modify an array while looping over it unless you know what you're doing.

---

**📚 Want to learn more?**

- 📘 *Eloquent JavaScript* – Chapter 2: Program Structure (Loops)
- 📘 *You Don’t Know JS (Scope & Closures)* – has loop behavior insights
- 🌐 javascript.info – “Loops: while and for”

---

## 6. Functions (`declaration`, `expression`, `arrow`)

**🧠 Definition:**

A **function** is a reusable block of code that performs a specific task. Functions can accept input (parameters) and return a result. There are three main ways to define functions in JavaScript: **function declaration**, **function expression**, and **arrow functions**.

---

**🧾 Syntax:**

```jsx
javascript
CopyEdit
// Function Declaration
function greet(name) {
  return `Hello, ${name}!`;
}

// Function Expression
const greet = function(name) {
  return `Hello, ${name}!`;
};

// Arrow Function (ES6)
const greet = (name) => {
  return `Hello, ${name}!`;
};

// Shorter Arrow Function Syntax
const greet = name => `Hello, ${name}!`;

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
// Function Declaration
function add(a, b) {
  return a + b;
}
console.log(add(5, 3)); // 8

// Function Expression
const multiply = function(a, b) {
  return a * b;
};
console.log(multiply(4, 2)); // 8

// Arrow Function
const subtract = (a, b) => a - b;
console.log(subtract(10, 5)); // 5

```

---

**✅ What to do with it:**

- Use **function declarations** for named functions that will be used throughout the code (hoisted).
- Use **function expressions** when you want to assign a function to a variable.
- Use **arrow functions** for shorter, cleaner syntax, especially in callbacks and higher-order functions.
- Remember that arrow functions don’t have their own `this`, they inherit it from the surrounding context.

---

**❌ What not to do with it:**

- ❌ Don’t use arrow functions if you need a new context for `this` (like in object methods).
- ❌ Don’t declare functions inside loops unless you need a new instance on each iteration.
- ❌ Don’t forget to return a value from a function if you want it to output something.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Scope & Closures)* – Chapter 4: Functions
- 📘 *Eloquent JavaScript* – Chapter 3: Functions
- 🌐 javascript.info – “Function expressions and declarations”

---

## 7. Scope & Hoisting

**🧠 Definition:**

**Scope** determines the accessibility of variables in different parts of the code. **Hoisting** is the behavior where variable and function declarations are moved to the top of their scope during execution.

---

**🧾 Syntax:**

```jsx
javascript
CopyEdit
// Example of Block Scope (let, const)
{
  let blockScoped = "I am block-scoped";
  console.log(blockScoped);  // "I am block-scoped"
}

console.log(blockScoped);  // ReferenceError: blockScoped is not defined

// Example of Function Scope (var)
function example() {
  var functionScoped = "I am function-scoped";
  console.log(functionScoped);  // "I am function-scoped"
}

console.log(functionScoped);  // ReferenceError: functionScoped is not defined

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
// Hoisting with var (function scope)
console.log(x);  // undefined (hoisted)
var x = 10;
console.log(x);  // 10

// Hoisting with let/const (block scope)
console.log(y);  // ReferenceError: Cannot access 'y' before initialization
let y = 20;

// Function Hoisting
greet();  // "Hello, world!"
function greet() {
  console.log("Hello, world!");
}

```

---

**🧑‍🏫 Explanation:**

- **Scope Types:**
    - **Global Scope**: Variables declared outside any function or block are globally accessible.
    - **Function Scope**: Variables declared inside a function are only accessible within that function.
    - **Block Scope**: Variables declared with `let` and `const` are confined to the block in which they are declared (inside `{}`).
- **Hoisting**:
    - **Function Declarations** are hoisted completely, so you can call them before they are written in the code.
    - **Var Declarations** are hoisted, but their initializations are not. This means they are undefined until the line of code that assigns a value.
    - **Let/Const Declarations** are hoisted, but they are not initialized. Trying to access them before the declaration results in a `ReferenceError` (called the "temporal dead zone").

---

**✅ What to do with it:**

- Use `let` and `const` for block-scoped variables.
- Declare variables and functions at the top of their scope for clarity and to avoid hoisting confusion.
- Avoid using `var` unless necessary, since it can lead to hoisting issues and bugs.

---

**❌ What not to do with it:**

- ❌ Don’t declare variables in the middle of the code if possible — always declare them at the top to avoid hoisting confusion.
- ❌ Don’t use `var` for new code, unless you're working with legacy code or need function-scoping specifically.
- ❌ Don’t access variables declared with `let`/`const` before their declaration (in the "temporal dead zone").

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Scope & Closures)* – Chapter 1: Scope
- 📘 *Eloquent JavaScript* – Chapter 3: Functions (Scope and closures)
- 🌐 javascript.info – “Variable scope and closures”

---

## 8. Type Conversion & Coercion

**🧠 Definition:**

**Type Conversion** is the process of converting a value from one type to another, either explicitly (manual conversion) or implicitly (automatic conversion). **Coercion** refers to JavaScript’s automatic type conversion when performing operations with different data types.

---

**🧾 Syntax:**

**Manual Conversion (Type Casting):**

```jsx
javascript
CopyEdit
let num = "123";
let str = Number(num);    // String to number
let bool = Boolean(num);  // String to boolean
let obj = String(num);    // Number to string

```

**Automatic Conversion (Coercion):**

```jsx
javascript
CopyEdit
let x = "5" + 2;  // "52" (String + Number coerces number to string)
let y = "5" - 2;  // 3   (String - Number coerces string to number)
let z = 5 + true; // 6   (Boolean coerced to 1)
let w = "5" * "2"; // 10  (String coerced to number)

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
// Type Conversion (Manual)
let str = "200";
let num = Number(str);   // string to number
console.log(num);         // 200

let val = 1;
let booleanVal = Boolean(val);  // number to boolean (1 is truthy)
console.log(booleanVal);        // true

// Type Coercion (Automatic)
let result = "10" - 5;  // 5  (string "10" coerced to number)
console.log(result);

let coercedSum = "10" + 5;  // "105" (number 5 coerced to string)
console.log(coercedSum);

```

---

**🧑‍🏫 Explanation:**

- **Type Conversion**: You can manually convert a value to a different type using functions like `Number()`, `String()`, and `Boolean()`.
- **Type Coercion**: JavaScript will automatically convert types when performing operations between mismatched data types (e.g., `"5" + 2` results in `"52"` because it coerces `2` to a string).

**Common Coercion Scenarios:**

- When using `+`, JavaScript coerces numbers to strings if one of the operands is a string.
- When using , , `/`, JavaScript coerces strings to numbers.
- Boolean values are coerced into `false` for values like `0`, `""`, `null`, `undefined`, and `NaN`. Everything else is coerced to `true`.

---

**✅ What to do with it:**

- Use manual type conversion when you need to ensure correct data types.
- Be aware of type coercion behavior to avoid unexpected results, especially with mixed types.
- Use strict equality (`===`) to avoid issues caused by implicit type coercion.

---

**❌ What not to do with it:**

- ❌ Don’t rely on automatic coercion without understanding the potential pitfalls (e.g., `"10" - 5` is valid but may confuse).
- ❌ Don’t perform operations between mixed types without considering how JavaScript might coerce them.
- ❌ Avoid using loose equality (`==`), as it allows for coercion, which might lead to bugs.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Types & Grammar)* – Chapter 3: Types & Coercion
- 📘 *Eloquent JavaScript* – Chapter 4: Data Structures (Type coercion in operators)
- 🌐 javascript.info – “Type conversions”

---

## 9. Truthy and Falsy Values

**🧠 Definition:**

In JavaScript, a value is considered **truthy** if it evaluates to `true` in a boolean context and **falsy** if it evaluates to `false`. JavaScript automatically converts values to boolean when required (e.g., in conditionals), and understanding truthy and falsy values is important for controlling flow.

---

**🧾 Syntax:**

```jsx
javascript
CopyEdit
let truthyValue = "Hello";    // truthy
let falsyValue = 0;           // falsy

if (truthyValue) {
  console.log("This is truthy!");  // Runs
}

if (falsyValue) {
  console.log("This is falsy!");
} else {
  console.log("This is falsy!");  // Runs
}

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
// Truthy values
console.log(!!"non-empty string");  // true
console.log(!!42);                  // true
console.log(!![1, 2, 3]);           // true (arrays are truthy)
console.log(!!{});                  // true (objects are truthy)

// Falsy values
console.log(!!0);                   // false
console.log(!!NaN);                 // false
console.log(!!"" );                 // false (empty string)
console.log(!!null);                // false
console.log(!!undefined);           // false
console.log(!!false);               // false

```

---

**🧑‍🏫 Explanation:**

- **Falsy Values**: These are values that JavaScript considers as `false` in a boolean context. They include:
    - `false`
    - `0`
    - `NaN`
    - `""` (empty string)
    - `null`
    - `undefined`
- **Truthy Values**: These are all values that are not falsy, and they are treated as `true` when converted to a boolean. Some examples include:
    - Non-empty strings (`"hello"`, `" "`)
    - Numbers other than `0` (`1`, `1`, `42`)
    - Objects (`{}`, `[]`)
    - Functions
    - `true`

JavaScript uses **implicit coercion** to evaluate these values in boolean expressions, for example in `if` conditions.

---

**✅ What to do with it:**

- Use **truthy** and **falsy** values in conditionals to control logic based on the existence or truth of data.
- Remember that almost everything in JavaScript is truthy except the known falsy values.

---

**❌ What not to do with it:**

- ❌ Don’t confuse falsy values with values that are explicitly `false`. Even though `0` and `""` are falsy, they are not the same as `false`.
- ❌ Don’t use falsy values without knowing how JavaScript will interpret them (e.g., `0` as false).

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Types & Grammar)* – Chapter 2: Truthy and Falsy
- 📘 *Eloquent JavaScript* – Chapter 4: Data Structures (coercion to boolean)
- 🌐 javascript.info – “Truthy and Falsy values”

---

## 10. Arrays & Objects (Basic)

**🧠 Definition:**

- **Arrays** are ordered collections of values, indexed by integers starting from `0`.
- **Objects** are collections of key-value pairs, where the keys (properties) are strings (or Symbols), and the values can be any data type.

---

### **Arrays**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
let array = [1, 2, 3, 4, 5];

```

**📌 Example:**

```jsx
javascript
CopyEdit
let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]);  // "apple" (accessing by index)

fruits.push("date");     // Adding an element to the end
console.log(fruits);     // ["apple", "banana", "cherry", "date"]

fruits.pop();            // Removing the last element
console.log(fruits);     // ["apple", "banana", "cherry"]

fruits.shift();          // Removing the first element
console.log(fruits);     // ["banana", "cherry"]

```

---

### **Objects**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
let person = {
  name: "John",
  age: 30,
  city: "New York"
};

```

**📌 Example:**

```jsx
javascript
CopyEdit
let person = {
  name: "Alice",
  age: 25,
  greet: function() {
    console.log("Hello " + this.name);
  }
};

console.log(person.name);  // "Alice"
person.greet();            // "Hello Alice"

person.city = "London";    // Adding a new property
console.log(person.city);  // "London"

```

---

### **Key Differences:**

- **Arrays:**
    - **Ordered**: Each element has an index starting from `0`.
    - **Methods**: `push()`, `pop()`, `shift()`, `unshift()`, `splice()`, `slice()`, `forEach()`, etc.
    - **Access**: Elements are accessed using numerical indices (`arr[0]`, `arr[1]`, etc.).
- **Objects:**
    - **Unordered**: Key-value pairs, where keys are strings or symbols.
    - **Methods**: Can store functions as properties.
    - **Access**: Access values using keys (`obj.key`, `obj["key"]`).

---

**✅ What to do with it:**

- Use **arrays** when you need an ordered collection of items (e.g., list of numbers, strings).
- Use **objects** when you need to represent real-world entities with key-value pairs (e.g., user details, product properties).
- Arrays are particularly useful for storing data that needs to be iterated over in order.

---

**❌ What not to do with it:**

- ❌ Don’t use arrays for data that needs to be accessed by arbitrary keys. Use objects instead.
- ❌ Don’t mix arrays and objects when the data structure requires clear relationships between data (e.g., don’t store key-value pairs in arrays).

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Types & Grammar)* – Chapter 4: Objects & Arrays
- 📘 *Eloquent JavaScript* – Chapter 5: Data Structures (arrays and objects)
- 🌐 javascript.info – “Objects”

## 11. Object Methods (keys, values, entries, etc.)

**🧠 Definition:**

JavaScript objects have built-in methods that help in working with key-value pairs. These methods are used to access, modify, or iterate over the keys and values in an object.

---

### **Object.keys()**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
Object.keys(obj);

```

**📌 Example:**

```jsx
javascript
CopyEdit
let person = { name: "Alice", age: 25, city: "New York" };
let keys = Object.keys(person);
console.log(keys);  // ["name", "age", "city"]

```

- `Object.keys()` returns an array of the object's own enumerable property names (keys).

---

### **Object.values()**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
Object.values(obj);

```

**📌 Example:**

```jsx
javascript
CopyEdit
let person = { name: "Alice", age: 25, city: "New York" };
let values = Object.values(person);
console.log(values);  // ["Alice", 25, "New York"]

```

- `Object.values()` returns an array of the object's own enumerable property values.

---

### **Object.entries()**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
Object.entries(obj);

```

**📌 Example:**

```jsx
javascript
CopyEdit
let person = { name: "Alice", age: 25, city: "New York" };
let entries = Object.entries(person);
console.log(entries);  // [["name", "Alice"], ["age", 25], ["city", "New York"]]

```

- `Object.entries()` returns an array of the object's own enumerable `[key, value]` pairs.

---

### **Object.assign()**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
Object.assign(target, ...sources);

```

**📌 Example:**

```jsx
javascript
CopyEdit
let person = { name: "Alice", age: 25 };
let address = { city: "New York", country: "USA" };
let merged = Object.assign(person, address);
console.log(merged);  // { name: "Alice", age: 25, city: "New York", country: "USA" }

```

- `Object.assign()` copies the values of all enumerable properties from one or more source objects to a target object.

---

### **Object.freeze()**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
Object.freeze(obj);

```

**📌 Example:**

```jsx
javascript
CopyEdit
let person = { name: "Alice", age: 25 };
Object.freeze(person);

person.age = 30;  // This won't change the age as the object is frozen
console.log(person.age);  // 25

```

- `Object.freeze()` prevents modifications to an object (e.g., adding, removing, or changing properties).

---

### **Object.fromEntries()**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
Object.fromEntries(entries);

```

**📌 Example:**

```jsx
javascript
CopyEdit
let entries = [["name", "Alice"], ["age", 25]];
let person = Object.fromEntries(entries);
console.log(person);  // { name: "Alice", age: 25 }

```

- `Object.fromEntries()` transforms a list of key-value pairs into an object.

---

### **Other Methods:**

- **hasOwnProperty()**: Checks if an object has a specific property.
    
    ```jsx
    javascript
    CopyEdit
    let person = { name: "Alice", age: 25 };
    console.log(person.hasOwnProperty("name"));  // true
    
    ```
    
- **getOwnPropertyNames()**: Returns an array of all property names (including non-enumerable properties).
    
    ```jsx
    javascript
    CopyEdit
    let person = { name: "Alice", age: 25 };
    console.log(Object.getOwnPropertyNames(person));  // ["name", "age"]
    
    ```
    

---

**✅ What to do with it:**

- Use `Object.keys()`, `Object.values()`, and `Object.entries()` to iterate over objects or extract specific data.
- Use `Object.assign()` to merge objects.
- Use `Object.freeze()` to create immutable objects when needed.

---

**❌ What not to do with it:**

- ❌ Don’t modify objects directly when they are frozen using `Object.freeze()`.
- ❌ Don’t use `Object.assign()` to deeply merge objects, as it only performs a shallow copy.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (ES6 & Beyond)* – Chapter 4: Objects
- 📘 *Eloquent JavaScript* – Chapter 6: The Secret Life of Objects
- 🌐 javascript.info – “Objects”

## PHASE 2

---

## 1. Array Methods (map, filter, reduce, etc.)

**🧠 Definition:**

JavaScript arrays have many built-in methods that allow you to manipulate, transform, and filter data. The most common ones include `map()`, `filter()`, and `reduce()`. These methods enable functional programming paradigms and are very useful for handling data in a more concise and readable manner.

---

### **map()**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
let newArray = arr.map(callback(currentValue, index, array));

```

**📌 Example:**

```jsx
javascript
CopyEdit
let numbers = [1, 2, 3, 4, 5];
let doubled = numbers.map(num => num * 2);
console.log(doubled);  // [2, 4, 6, 8, 10]

```

- `map()` iterates over each element in the array, applies the provided callback function to each element, and returns a new array with the transformed values.

---

### **filter()**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
let newArray = arr.filter(callback(currentValue, index, array));

```

**📌 Example:**

```jsx
javascript
CopyEdit
let numbers = [1, 2, 3, 4, 5, 6];
let evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers);  // [2, 4, 6]

```

- `filter()` iterates over each element and filters the array based on the condition in the callback function, returning a new array with elements that meet the condition.

---

### **reduce()**

**🧾 Syntax:**

```jsx
javascript
CopyEdit
let result = arr.reduce(callback(accumulator, currentValue, index, array), initialValue);

```

**📌 Example:**

```jsx
javascript
CopyEdit
let numbers = [1, 2, 3, 4, 5];
let sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum);  // 15

```

- `reduce()` applies the callback function to each element in the array, accumulating a result (e.g., sum, product). The `accumulator` stores the intermediate result, and you can specify an `initialValue` for it.

---

### **Other Array Methods**

- **forEach()**: Executes a function on each element of the array (does not return a new array).
    
    ```jsx
    javascript
    CopyEdit
    let numbers = [1, 2, 3, 4];
    numbers.forEach(num => console.log(num));  // 1 2 3 4
    
    ```
    
- **some()**: Checks if at least one element in the array meets the condition.
    
    ```jsx
    javascript
    CopyEdit
    let numbers = [1, 2, 3, 4];
    let hasEven = numbers.some(num => num % 2 === 0);
    console.log(hasEven);  // true
    
    ```
    
- **every()**: Checks if all elements in the array meet the condition.
    
    ```jsx
    javascript
    CopyEdit
    let numbers = [2, 4, 6, 8];
    let allEven = numbers.every(num => num % 2 === 0);
    console.log(allEven);  // true
    
    ```
    
- **find()**: Returns the first element that satisfies the condition.
    
    ```jsx
    javascript
    CopyEdit
    let numbers = [1, 2, 3, 4];
    let firstEven = numbers.find(num => num % 2 === 0);
    console.log(firstEven);  // 2
    
    ```
    
- **sort()**: Sorts the array in place.
    
    ```jsx
    javascript
    CopyEdit
    let numbers = [4, 2, 8, 1];
    numbers.sort((a, b) => a - b);
    console.log(numbers);  // [1, 2, 4, 8]
    
    ```
    

---

**✅ What to do with it:**

- Use `map()` when you need to transform each element of an array and return a new array.
- Use `filter()` when you need to extract elements from an array based on a condition.
- Use `reduce()` when you need to accumulate values (like summing numbers, concatenating strings, etc.).
- Use `forEach()` for side effects (like logging or updating UI) but avoid using it for transformations.
- `some()` and `every()` are great for checking conditions across all or any elements of the array.

---

**❌ What not to do with it:**

- ❌ Don’t use `forEach()` when you need a new array as it doesn’t return one.
- ❌ Don’t use `map()` if you're not returning a transformed value for each element.
- ❌ Don’t forget that `reduce()` can sometimes be overused. It’s very powerful but can lead to less readable code if the logic is too complex.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (ES6 & Beyond)* – Chapter 5: Iteration (Array methods)
- 📘 *Eloquent JavaScript* – Chapter 5: Higher-order functions
- 🌐 javascript.info – “Array methods”

## 2. Callback Functions

**🧠 Definition:**

A **callback function** is a function that is passed as an argument to another function and is executed (or "called back") after the completion of that function’s task. This allows you to run custom code once a certain operation is finished.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
function someFunction(callback) {
  // do some work
  callback();
}

```

**📌 Example:**

```jsx
javascript
CopyEdit
function greet(name, callback) {
  console.log("Hello, " + name);
  callback();
}

function afterGreeting() {
  console.log("Greeting done!");
}

greet("Alice", afterGreeting);
// Output:
// Hello, Alice
// Greeting done!

```

- In this example, `afterGreeting` is the callback function passed to `greet`. Once the `greet` function finishes logging the greeting, it calls `afterGreeting` to indicate that the task is done.

---

### **🧾 Callback with Parameters:**

You can also pass parameters to the callback function.

**📌 Example:**

```jsx
javascript
CopyEdit
function processUserData(name, age, callback) {
  console.log(`Processing data for ${name}, Age: ${age}`);
  callback(name, age);
}

function displayUserInfo(name, age) {
  console.log(`${name} is ${age} years old.`);
}

processUserData("Alice", 30, displayUserInfo);
// Output:
// Processing data for Alice, Age: 30
// Alice is 30 years old.

```

- Here, `displayUserInfo` is the callback that receives parameters passed from `processUserData`.

---

### **Common Uses of Callback Functions:**

1. **Asynchronous Operations:**
    
    Callbacks are heavily used in asynchronous programming, such as with `setTimeout()`, event handlers, or AJAX requests.
    
    **📌 Example (setTimeout):**
    
    ```jsx
    javascript
    CopyEdit
    setTimeout(() => {
      console.log("This runs after 2 seconds!");
    }, 2000);
    
    ```
    
2. **Array Methods:**
    
    Functions like `map()`, `filter()`, `forEach()`, etc., rely on callbacks to handle each element of an array.
    
    **📌 Example (Array map):**
    
    ```jsx
    javascript
    CopyEdit
    let numbers = [1, 2, 3];
    let doubled = numbers.map(num => num * 2);
    console.log(doubled);  // [2, 4, 6]
    
    ```
    

---

### **🧾 Callback Functions in Asynchronous Code:**

Callbacks are commonly used in asynchronous code (e.g., reading files, making HTTP requests) to continue execution after an operation completes.

**📌 Example (Simulating a file read):**

```jsx
javascript
CopyEdit
function readFile(callback) {
  setTimeout(() => {
    console.log("File read successfully!");
    callback();
  }, 2000);
}

function processFile() {
  console.log("Processing the file...");
}

readFile(processFile);
// Output:
// File read successfully!
// Processing the file...

```

---

### **✅ What to do with it:**

- Use callbacks to handle asynchronous operations like network requests, time delays, or reading files.
- Callbacks are also handy for events (like button clicks) or iterating over arrays with methods like `map()`, `filter()`, and `forEach()`.

---

### **❌ What not to do with it:**

- ❌ Avoid "callback hell" or deeply nested callbacks. This makes code hard to maintain. Instead, consider using Promises or async/await for cleaner, more readable code.
- ❌ Don’t use callbacks for simple synchronous operations. You can use functions directly instead of passing them around as arguments.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Callbacks & Closures)* – Chapter 2: Functions
- 📘 *Eloquent JavaScript* – Chapter 3: Functions
- 🌐 javascript.info – “Callbacks”

---

## 3. Closures

**🧠 Definition:**

A **closure** is a function that "remembers" its lexical scope even when the function is executed outside of that scope. This means that a function can access variables from its outer (enclosing) function even after the outer function has finished execution.

In simpler terms, a closure gives you access to variables from an outer function even when the outer function has already returned.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
function outerFunction() {
  let outerVariable = "I am outside!";

  function innerFunction() {
    console.log(outerVariable);  // innerFunction has access to outerVariable
  }

  return innerFunction;
}

let closureFunction = outerFunction();
closureFunction();  // Output: "I am outside!"

```

- Here, `innerFunction` is a closure because it can access `outerVariable` even after `outerFunction` has finished execution.

---

### **📌 Example 1: Basic Closure**

```jsx
javascript
CopyEdit
function createCounter() {
  let count = 0;  // `count` is a variable in the outer function

  return function() {  // inner function has access to `count`
    count++;
    console.log(count);
  };
}

const counter = createCounter();
counter();  // Output: 1
counter();  // Output: 2
counter();  // Output: 3

```

- Here, `counter` is a closure that remembers and updates the `count` variable even though `createCounter()` has finished executing. Every time `counter()` is called, it has access to the `count` variable.

---

### **📌 Example 2: Closure with Arguments**

```jsx
javascript
CopyEdit
function multiplier(factor) {
  return function(num) {
    return num * factor;
  };
}

const double = multiplier(2);  // Closure that multiplies by 2
console.log(double(5));  // Output: 10

const triple = multiplier(3);  // Closure that multiplies by 3
console.log(triple(5));  // Output: 15

```

- In this example, `double` and `triple` are closures that "remember" their respective `factor` values, allowing them to multiply numbers by 2 and 3.

---

### **📌 Example 3: Using Closures for Data Encapsulation**

```jsx
javascript
CopyEdit
function createBankAccount() {
  let balance = 0;  // `balance` is private to the closure

  return {
    deposit(amount) {
      balance += amount;
      console.log(`Deposited: ${amount}, New Balance: ${balance}`);
    },
    withdraw(amount) {
      balance -= amount;
      console.log(`Withdrew: ${amount}, New Balance: ${balance}`);
    },
    getBalance() {
      return balance;
    }
  };
}

const account = createBankAccount();
account.deposit(100);  // Deposited: 100, New Balance: 100
account.withdraw(50);  // Withdrew: 50, New Balance: 50
console.log(account.getBalance());  // 50

```

- The `balance` is private to the `createBankAccount` closure, ensuring it cannot be accessed or modified directly from outside the closure, but can only be changed via the provided methods.

---

### **🧾 How Closures Work Internally:**

When a function is executed, it creates a "scope" for its variables. A closure happens when a function is returned and has access to the variables in its outer function, even after the outer function has finished executing.

In the above example:

- `createBankAccount()` creates a scope for the `balance` variable.
- The methods `deposit()`, `withdraw()`, and `getBalance()` retain access to `balance` even after `createBankAccount()` returns.

---

### **✅ What to do with it:**

- Use closures to create private variables or encapsulate state, keeping internal data hidden from the outside world.
- Leverage closures for functions like event handlers, callbacks, and factory functions that need to maintain state across multiple calls.

---

### **❌ What not to do with it:**

- ❌ Don’t overuse closures for simple scenarios, as they can introduce unnecessary complexity.
- ❌ Avoid memory leaks when using closures by ensuring that you don't unintentionally retain references to objects or data that are no longer needed.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Closures)* – Chapter 3: Closures
- 📘 *Eloquent JavaScript* – Chapter 3: Functions
- 🌐 javascript.info – “Closures”

---

## 4. The `this` Keyword

**🧠 Definition:**

The `this` keyword in JavaScript refers to the object that is currently executing the code. It’s used to access properties or methods of the object in which the function is being executed.

The value of `this` depends on how a function is called. It can refer to different objects based on the context of the function call.

---

### **🧾 How `this` Works in Different Contexts:**

### 1. **Global Context**

- When used in the global execution context (outside of any function or object), `this` refers to the global object (`window` in browsers, `global` in Node.js).

**📌 Example:**

```jsx
javascript
CopyEdit
console.log(this);  // In the browser, this refers to the global window object

```

### 2. **Inside a Function (Regular Function)**

- In a regular function (not an arrow function), `this` refers to the global object (or `undefined` in strict mode).

**📌 Example:**

```jsx
javascript
CopyEdit
function show() {
  console.log(this);  // In non-strict mode, this refers to the global object
}

show();

```

- **Note:** In strict mode, `this` will be `undefined` inside a regular function:
    
    ```jsx
    javascript
    CopyEdit
    'use strict';
    function show() {
      console.log(this);  // undefined in strict mode
    }
    show();
    
    ```
    

### 3. **Inside an Object (Method)**

- When `this` is used inside a method (a function within an object), it refers to the object the method is called on.

**📌 Example:**

```jsx
javascript
CopyEdit
let person = {
  name: "Alice",
  greet: function() {
    console.log(this.name);  // this refers to the person object
  }
};

person.greet();  // Output: Alice

```

- Here, `this` refers to the `person` object, and we can access the `name` property through `this.name`.

### 4. **Inside a Constructor Function**

- When `this` is used inside a constructor function (with the `new` keyword), it refers to the newly created object.

**📌 Example:**

```jsx
javascript
CopyEdit
function Person(name) {
  this.name = name;
}

let alice = new Person("Alice");
console.log(alice.name);  // Output: Alice

```

- `this` refers to the newly created object `alice`.

### 5. **Arrow Functions**

- Arrow functions do **not** have their own `this`. Instead, `this` in an arrow function is lexically inherited from the surrounding context (the `this` value of the enclosing function).

**📌 Example:**

```jsx
javascript
CopyEdit
let person = {
  name: "Alice",
  greet: function() {
    setTimeout(() => {
      console.log(this.name);  // this refers to the person object because arrow function inherits the this value
    }, 1000);
  }
};

person.greet();  // Output: Alice (after 1 second)

```

- In this example, the arrow function inside `setTimeout()` inherits `this` from the `greet` method.

### 6. **Explicit Binding (call, apply, bind)**

- You can explicitly set the value of `this` using the `call()`, `apply()`, and `bind()` methods.

**📌 Example (call):**

```jsx
javascript
CopyEdit
function greet() {
  console.log(`Hello, ${this.name}`);
}

let person = { name: "Alice" };

greet.call(person);  // Output: Hello, Alice

```

- The `call()` method allows you to explicitly specify the value of `this` for the function.

**📌 Example (bind):**

```jsx
javascript
CopyEdit
let greetPerson = greet.bind(person);
greetPerson();  // Output: Hello, Alice

```

- `bind()` returns a new function where `this` is permanently set to the object passed to `bind()`.

---

### **✅ What to do with it:**

- Use `this` to refer to the object the method belongs to, and to set or get properties in object methods.
- Understand how `this` behaves differently in arrow functions, constructor functions, and regular functions.
- Use `call()`, `apply()`, and `bind()` to control the context (`this`) when needed.

---

### **❌ What not to do with it:**

- ❌ Don’t confuse `this` inside arrow functions with regular functions. Arrow functions inherit `this` from their enclosing scope.
- ❌ Avoid relying too much on the global object for `this`, as it may lead to bugs and unintentional side effects, especially in strict mode.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (this & Object Prototypes)* – Chapter 2: this
- 📘 *Eloquent JavaScript* – Chapter 4: Objects
- 🌐 javascript.info – “this”

## 5. Object-Oriented JavaScript (Prototypes, Inheritance)

**🧠 Definition:**
Object-Oriented Programming (OOP) in JavaScript revolves around objects, classes, and inheritance. In JavaScript, the prototype chain is the foundation of inheritance. Every JavaScript object has a prototype, which is another object from which it inherits properties and methods.

---

### **1. Prototypes:**

**🧠 Definition:**
Every object in JavaScript has an internal property called `[[Prototype]]`, which points to another object. This is known as the object's prototype. The prototype itself can also have its own prototype, creating a chain called the **prototype chain**.

Objects inherit methods and properties from their prototype. When you try to access a property or method on an object, JavaScript first checks if it exists on the object itself. If not, it looks for it in the object's prototype, and so on.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
let obj = {};
console.log(obj.__proto__);  // This is the prototype of `obj`

```

- `__proto__` is a non-standard way to access the prototype (for demonstration). In modern JavaScript, the recommended way to work with prototypes is through `Object.getPrototypeOf()`.

---

### **📌 Example 1: Basic Prototype Chain**

```jsx
javascript
CopyEdit
let animal = {
  eat() {
    console.log("Eating...");
  }
};

let dog = Object.create(animal);  // `dog` inherits from `animal`

dog.bark = function() {
  console.log("Barking...");
};

dog.bark();  // Output: Barking...
dog.eat();   // Output: Eating...

```

- Here, `dog` inherits from `animal` via `Object.create()`, so `dog` has access to the `eat()` method of `animal`.

---

### **2. Inheritance with Constructor Functions:**

Before ES6 classes, JavaScript used **constructor functions** to create objects. These functions could also establish prototype-based inheritance.

---

### **🧾 Constructor Function Syntax:**

```jsx
javascript
CopyEdit
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a noise.`);
};

let dog = new Animal('Dog');
dog.speak();  // Output: Dog makes a noise.

```

- In this example, `dog` is created by the `Animal` constructor, and it inherits the `speak()` method from `Animal.prototype`.

---

### **📌 Example 2: Inheritance with Constructor Functions**

```jsx
javascript
CopyEdit
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a noise.`);
};

function Dog(name) {
  Animal.call(this, name);  // Call the parent constructor
}

Dog.prototype = Object.create(Animal.prototype);  // Set the prototype chain
Dog.prototype.constructor = Dog;  // Restore the constructor

let dog = new Dog('Buddy');
dog.speak();  // Output: Buddy makes a noise.

```

- In this example, `Dog` inherits from `Animal`. The `call()` method is used to call the `Animal` constructor from within `Dog`, and `Object.create()` is used to establish the inheritance chain.

---

### **3. ES6 Classes:**

With ES6, JavaScript introduced the `class` syntax, which is more syntactically elegant and easier to understand, but it's still based on prototypes under the hood.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name) {
    super(name);  // Call the parent constructor
  }
}

let dog = new Dog('Buddy');
dog.speak();  // Output: Buddy makes a noise.

```

- In this ES6 example, `Dog` extends `Animal` using the `extends` keyword. The `super()` method calls the constructor of the parent class.

---

### **📌 Example 3: Inheritance with ES6 Classes**

```jsx
javascript
CopyEdit
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);  // Call the parent constructor
    this.breed = breed;
  }

  speak() {
    console.log(`${this.name} barks.`);
  }
}

let dog = new Dog('Buddy', 'Labrador');
dog.speak();  // Output: Buddy barks.

```

- In this example, `Dog` inherits from `Animal`, but it also overrides the `speak()` method to provide its own behavior.

---

### **4. Prototypal Inheritance in Action:**

The prototype chain enables inheritance in JavaScript. When you access a property or method on an object, JavaScript first checks if the property exists on the object itself. If not, it checks the object's prototype, and so on.

---

### **📌 Example 4: Prototypal Inheritance in Action**

```jsx
javascript
CopyEdit
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a noise.`);
};

function Dog(name) {
  Animal.call(this, name);  // Call the parent constructor
}

Dog.prototype = Object.create(Animal.prototype);  // Set prototype
Dog.prototype.constructor = Dog;

let dog = new Dog('Buddy');
console.log(dog.__proto__);  // Output: Dog { constructor: [Function: Dog] }

```

- The `dog` object inherits from the `Animal` prototype, and you can trace the inheritance through the prototype chain.

---

### **✅ What to do with it:**

- Use constructor functions or ES6 classes for creating objects and establishing inheritance.
- Leverage prototypes to share methods and properties across instances without duplicating them.

---

### **❌ What not to do with it:**

- ❌ Avoid unnecessary inheritance if composition (using objects or modules) is more appropriate for your design.
- ❌ Don’t forget to set `constructor` correctly when manipulating prototype chains manually (this is automatically handled by ES6 classes).

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (this & Object Prototypes)* – Chapter 4: Prototypes
- 📘 *Eloquent JavaScript* – Chapter 6: The Secret Life of Objects
- 🌐 javascript.info – “Prototype Inheritance”

---

## 6. ES6+ Features (Destructuring, Spread, etc.)

ES6 (ECMAScript 2015) and later versions introduced several features that modernized JavaScript. Let’s go over some of the most commonly used features, like **Destructuring**, **Spread**, **Rest**, **Arrow Functions**, and more.

---

### **1. Destructuring**

**🧠 Definition:**

Destructuring allows you to unpack values from arrays or properties from objects into distinct variables. It simplifies extracting values from complex structures.

---

### **🧾 Syntax for Arrays:**

```jsx
javascript
CopyEdit
let arr = [1, 2, 3];
let [a, b] = arr;

console.log(a);  // Output: 1
console.log(b);  // Output: 2

```

- You can also skip elements or assign default values.

```jsx
javascript
CopyEdit
let arr = [1, 2];
let [a, , c = 3] = arr;

console.log(a);  // Output: 1
console.log(c);  // Output: 3 (default value)

```

---

### **🧾 Syntax for Objects:**

```jsx
javascript
CopyEdit
let person = { name: "Alice", age: 25 };
let { name, age } = person;

console.log(name);  // Output: Alice
console.log(age);   // Output: 25

```

- You can also rename variables:

```jsx
javascript
CopyEdit
let person = { name: "Alice", age: 25 };
let { name: fullName, age: yearsOld } = person;

console.log(fullName);  // Output: Alice
console.log(yearsOld);  // Output: 25

```

---

### **2. Spread Operator (`...`)**

**🧠 Definition:**

The spread operator (`...`) allows you to unpack elements from an array or properties from an object and spread them into a new array or object.

---

### **🧾 Syntax for Arrays:**

```jsx
javascript
CopyEdit
let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];

console.log(arr2);  // Output: [1, 2, 3, 4, 5]

```

- You can use the spread operator to combine arrays or copy arrays without modifying the original.

---

### **🧾 Syntax for Objects:**

```jsx
javascript
CopyEdit
let obj1 = { a: 1, b: 2 };
let obj2 = { ...obj1, c: 3 };

console.log(obj2);  // Output: { a: 1, b: 2, c: 3 }

```

- You can also use it to create shallow copies of objects or merge multiple objects.

---

### **3. Rest Parameter (`...`)**

**🧠 Definition:**

The rest parameter (`...`) allows you to collect a variable number of arguments into an array.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3));  // Output: 6
console.log(sum(4, 5, 6, 7, 8));  // Output: 30

```

- The rest parameter collects all remaining arguments passed to the function.

---

### **4. Arrow Functions**

**🧠 Definition:**

Arrow functions are a more concise syntax for writing functions. They do not have their own `this` and inherit it from the surrounding context.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
let add = (a, b) => a + b;

console.log(add(2, 3));  // Output: 5

```

- Arrow functions are especially useful for short functions.

---

### **5. Template Literals**

**🧠 Definition:**

Template literals make string interpolation easier. They allow embedded expressions and multi-line strings.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
let name = "Alice";
let greeting = `Hello, ${name}!`;

console.log(greeting);  // Output: Hello, Alice!

```

- You can also create multi-line strings:

```jsx
javascript
CopyEdit
let multiLine = `This is
a multi-line
string.`;

console.log(multiLine);

```

---

### **6. Classes**

**🧠 Definition:**

ES6 introduced `class` syntax, which is a more readable and syntactically cleaner way to define constructor functions and methods for objects.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);
  }
}

let person = new Person("Alice", 25);
person.greet();  // Output: Hello, my name is Alice and I'm 25 years old.

```

- Classes provide a cleaner way to define prototypes and inheritance.

---

### **7. Default Parameters**

**🧠 Definition:**

Default parameters allow you to set default values for function parameters if no value is provided.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
function greet(name = "Guest") {
  console.log(`Hello, ${name}!`);
}

greet("Alice");  // Output: Hello, Alice!
greet();         // Output: Hello, Guest!

```

- You can assign default values to parameters that aren’t passed.

---

### **✅ What to do with it:**

- Use **destructuring** to easily extract values from arrays and objects.
- Use the **spread operator** to copy, merge, or clone arrays and objects.
- Use **rest parameters** for functions that can accept a variable number of arguments.
- Write concise, readable code with **arrow functions** and **template literals**.

---

### **❌ What not to do with it:**

- ❌ Avoid using **arrow functions** for methods that need their own `this` (e.g., in object methods).
- ❌ Don't forget that **spread** only creates a shallow copy. Nested objects/arrays will still refer to the same references.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (ES6 & Beyond)* – Chapter 2: ES6 Features
- 📘 *Eloquent JavaScript* – Chapter 5: Higher-Order Functions
- 🌐 [javascript.info](https://javascript.info/) – “ES6 Features”

## 7. Error Handling (`try...catch`, `throw`, `finally`)

**🧠 Definition:**

**Error handling** allows you to catch and respond to runtime errors to ensure your code behaves gracefully even when something goes wrong. JavaScript provides the `try...catch` statement to handle errors, along with `throw` for creating custom errors and `finally` for executing code that runs regardless of whether an error occurred.

---

**🧾 Syntax:**

```jsx
javascript
CopyEdit
// try...catch
try {
  // code that may throw an error
  let result = riskyFunction();
} catch (error) {
  // code to handle the error
  console.log("Error caught:", error.message);
} finally {
  // code that runs regardless of an error
  console.log("This runs no matter what!");
}

// throw
throw new Error("Something went wrong!");

```

---

**📌 Example:**

```jsx
javascript
CopyEdit
// try...catch example
try {
  let number = 10;
  let result = number / 0;  // Infinity, but no error
  console.log(result);
} catch (error) {
  console.log("An error occurred: ", error.message);  // won't run
} finally {
  console.log("This code runs no matter what!");  // Always runs
}

// throw example
function validateNumber(num) {
  if (num < 0) {
    throw new Error("Number must be positive");
  }
  return num;
}

try {
  validateNumber(-5);  // This will throw an error
} catch (error) {
  console.log(error.message);  // "Number must be positive"
}

```

---

**🧑‍🏫 Explanation:**

- **try...catch**: The `try` block contains code that may throw an error. If an error occurs, it jumps to the `catch` block where you can handle the error. The `finally` block runs no matter what, useful for cleanup tasks (like closing files or releasing resources).
- **throw**: You can manually throw an error using the `throw` statement, which allows you to generate custom error messages.

---

**✅ What to do with it:**

- Use `try...catch` to gracefully handle unexpected errors and avoid crashes.
- Use `throw` to raise errors when your code encounters invalid or unexpected input.
- Always include a `finally` block for cleanup or logging purposes.
- Consider logging the error details in production environments (using a logger).

---

**❌ What not to do with it:**

- ❌ Don’t use `try...catch` for regular control flow (only for exceptional cases).
- ❌ Don’t throw generic errors — provide meaningful messages that help diagnose issues.
- ❌ Don’t catch errors unless you have a specific plan for handling them. Catching errors without action can hide issues.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Async & Performance)* – Chapter 7: Error Handling
- 📘 *Eloquent JavaScript* – Chapter 10: Asynchronous Programming (handling asynchronous errors)
- 🌐 javascript.info – “Error handling: try..catch”

---

## Timers (setTimeout, setInterval)

Timers are functions that allow you to execute code after a certain amount of time or repeatedly at specified intervals. They are helpful for tasks like animations, periodic updates, or deferred code execution.

---

### **1. `setTimeout()`**

**🧠 Definition:**

`setTimeout()` allows you to execute a function after a specified delay (in milliseconds). It runs the code **once** after the delay.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
setTimeout(function, delay, [arguments]);

```

- `function`: The function to be executed.
- `delay`: The time in milliseconds before executing the function.
- `[arguments]`: Optional arguments to be passed to the function.

---

### **📌 Example 1: Simple `setTimeout()`**

```jsx
javascript
CopyEdit
setTimeout(() => {
  console.log("Hello after 2 seconds");
}, 2000);

```

- This will log "Hello after 2 seconds" after a delay of 2000 milliseconds (2 seconds).

---

### **📌 Example 2: `setTimeout()` with Arguments**

```jsx
javascript
CopyEdit
function greet(name) {
  console.log(`Hello, ${name}!`);
}

setTimeout(greet, 2000, "Alice");  // Output: Hello, Alice!

```

- Here, the function `greet` is called after 2 seconds, and "Alice" is passed as an argument.

---

### **2. `clearTimeout()`**

**🧠 Definition:**

If you want to cancel a `setTimeout()` before it runs, you can use `clearTimeout()`. This is useful if the condition changes and you no longer want the function to execute.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
let timeoutId = setTimeout(() => {
  console.log("This won't run.");
}, 5000);

clearTimeout(timeoutId);  // Cancels the timeout

```

- `timeoutId` is the identifier returned by `setTimeout()` and is used to cancel the timeout before it executes.

---

### **3. `setInterval()`**

**🧠 Definition:**

`setInterval()` allows you to execute a function repeatedly at a specified interval (in milliseconds). The function runs continuously at the defined interval.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
setInterval(function, interval, [arguments]);

```

- `function`: The function to be executed.
- `interval`: The time in milliseconds between each function call.
- `[arguments]`: Optional arguments to be passed to the function.

---

### **📌 Example 1: Simple `setInterval()`**

```jsx
javascript
CopyEdit
let count = 0;
let intervalId = setInterval(() => {
  count++;
  console.log(`Count: ${count}`);
  if (count === 5) {
    clearInterval(intervalId);  // Stops after 5 counts
  }
}, 1000);  // Output: Count: 1, Count: 2, ..., Count: 5

```

- In this example, the counter increments every second and stops after reaching 5.

---

### **📌 Example 2: `setInterval()` with Arguments**

```jsx
javascript
CopyEdit
function greet(name) {
  console.log(`Hello, ${name}!`);
}

let intervalId = setInterval(greet, 2000, "Bob");  // Output: Hello, Bob! every 2 seconds

```

- The `greet` function is executed every 2 seconds with "Bob" as the argument.

---

### **4. `clearInterval()`**

**🧠 Definition:**

You can use `clearInterval()` to stop the repeated execution of a function set by `setInterval()`.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
let intervalId = setInterval(() => {
  console.log("This will stop soon.");
}, 1000);

clearInterval(intervalId);  // Stops the interval immediately

```

- `intervalId` is the identifier returned by `setInterval()`, and you use it to stop the interval.

---

### **✅ What to do with it:**

- Use **`setTimeout()`** for delaying a single action.
- Use **`setInterval()`** for repeating actions at regular intervals (e.g., updating a timer, checking server status).
- Use **`clearTimeout()`** and **`clearInterval()`** to cancel scheduled actions.

---

### **❌ What not to do with it:**

- ❌ Don’t forget to clear intervals (`clearInterval()`) when they are no longer needed to avoid memory leaks.
- ❌ Avoid using **long intervals** or **timeouts** that are too frequent or not cleared, as they can cause performance issues.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Async & Performance)* – Chapter 5: Timers and Delays
- 📘 *Eloquent JavaScript* – Chapter 11: Asynchronous Programming
- 🌐 javascript.info – “setTimeout, setInterval”

## PHASE 3

---

## 1. Promises & Async/Await

Asynchronous operations are common in JavaScript, such as fetching data from a server or reading files. **Promises** and **Async/Await** make it easier to work with asynchronous code and avoid issues like callback hell.

---

### **1. Promises**

**🧠 Definition:**

A **Promise** is an object representing the eventual completion (or failure) of an asynchronous operation. It allows you to handle asynchronous operations in a more structured way.

---

### **🧾 Promise States:**

1. **Pending**: The initial state, before the promise is resolved or rejected.
2. **Fulfilled**: The operation completed successfully.
3. **Rejected**: The operation failed.

---

### **🧾 Syntax for Creating a Promise:**

```jsx
javascript
CopyEdit
let promise = new Promise((resolve, reject) => {
  let success = true;  // Change this to false to test rejection

  if (success) {
    resolve("Operation successful!");
  } else {
    reject("Operation failed!");
  }
});

```

- The promise takes a function with two parameters: `resolve` (if the operation is successful) and `reject` (if there’s an error).

---

### **📌 Example 1: Handling a Fulfilled Promise**

```jsx
javascript
CopyEdit
let promise = new Promise((resolve, reject) => {
  resolve("Data fetched successfully!");
});

promise.then((result) => {
  console.log(result);  // Output: Data fetched successfully!
}).catch((error) => {
  console.log(error);
});

```

- The `.then()` method is called if the promise is fulfilled, while `.catch()` handles rejections.

---

### **📌 Example 2: Handling a Rejected Promise**

```jsx
javascript
CopyEdit
let promise = new Promise((resolve, reject) => {
  reject("Failed to fetch data!");
});

promise.then((result) => {
  console.log(result);
}).catch((error) => {
  console.log(error);  // Output: Failed to fetch data!
});

```

- `.catch()` is triggered when the promise is rejected.

---

### **2. Async/Await**

**🧠 Definition:**

`Async` and `await` are syntactic sugar over promises. They allow you to write asynchronous code that looks and behaves more like synchronous code.

- **`async`**: Makes a function return a promise.
- **`await`**: Pauses the execution of the `async` function until the promise is resolved.

---

### **🧾 Syntax for Async Function:**

```jsx
javascript
CopyEdit
async function fetchData() {
  return "Data fetched!";
}

```

- An `async` function always returns a promise, which resolves to the return value of the function.

---

### **📌 Example 1: Using Async/Await**

```jsx
javascript
CopyEdit
async function fetchData() {
  let response = await new Promise((resolve) => {
    setTimeout(() => resolve("Data fetched!"), 2000);
  });

  console.log(response);  // Output: Data fetched!
}

fetchData();

```

- The `await` keyword pauses the function’s execution until the promise is resolved.

---

### **📌 Example 2: Handling Errors with Async/Await**

```jsx
javascript
CopyEdit
async function fetchData() {
  try {
    let response = await new Promise((resolve, reject) => {
      reject("Failed to fetch data!");
    });

    console.log(response);
  } catch (error) {
    console.log(error);  // Output: Failed to fetch data!
  }
}

fetchData();

```

- Use `try...catch` blocks to handle errors with `async/await`.

---

### **3. Chaining Promises with Async/Await**

**🧠 Definition:**

With `async/await`, you can chain multiple asynchronous operations in a more readable manner.

---

### **📌 Example: Chaining Async Functions**

```jsx
javascript
CopyEdit
async function fetchData() {
  let data = await new Promise((resolve) => resolve("Fetched data"));
  console.log(data);

  let result = await new Promise((resolve) => resolve("Processed data"));
  console.log(result);

  return "Done!";
}

fetchData().then((finalResult) => {
  console.log(finalResult);  // Output: Done!
});

```

- Each `await` waits for the previous promise to resolve before moving to the next line.

---

### **4. Promise.all()**

**🧠 Definition:**

`Promise.all()` is used when you want to wait for multiple promises to resolve simultaneously. It returns a single promise that resolves when all of the input promises are fulfilled.

---

### **🧾 Syntax:**

```jsx
javascript
CopyEdit
let promise1 = Promise.resolve("Data 1");
let promise2 = Promise.resolve("Data 2");

Promise.all([promise1, promise2]).then((results) => {
  console.log(results);  // Output: ["Data 1", "Data 2"]
});

```

---

### **✅ What to do with it:**

- Use **`async/await`** for cleaner, more readable asynchronous code.
- Use **`Promise.all()`** when you need to wait for multiple promises to resolve at once.
- Handle errors using **`try...catch`** in `async` functions for better control over failures.

---

### **❌ What not to do with it:**

- ❌ Don’t forget that **`async` functions** always return a promise, so be careful when handling return values.
- ❌ Avoid using `await` outside of an `async` function.
- ❌ Don’t use **`await`** in a loop if the promises don't need to run sequentially—use **`Promise.all()`** for parallel execution instead.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Async & Performance)* – Chapter 3: Promises
- 📘 *Eloquent JavaScript* – Chapter 11: Asynchronous Programming
- 🌐 javascript.info – “Async functions”

---

## 2. Event Loop & Call Stack

---

### **1. Call Stack**

**🧠 Definition:**

The **Call Stack** is a data structure used by the JavaScript engine to keep track of function execution. It works on the **LIFO** principle (Last In, First Out).

---

### **🧾 Syntax/Behavior:**

- When a function is invoked, it’s pushed onto the stack.
- When it finishes executing, it's popped off the stack.

---

### **📌 Example:**

```jsx
javascript
CopyEdit
function first() {
  second();
  console.log("First");
}

function second() {
  console.log("Second");
}

first();
// Output:
// Second
// First

```

**Stack Flow:**

1. `first()` is called → pushed to stack.
2. `second()` is called from inside `first()` → pushed to stack.
3. `second()` logs and finishes → popped off.
4. `first()` continues and logs → popped off.

---

### ✅ What to do:

- Use the stack to trace function calls during debugging.
- Understand stack overflow: happens when too many functions are called recursively without exiting.

---

### ❌ What not to do:

- ❌ Don’t write infinite recursion—it will crash the browser:
    
    ```jsx
    javascript
    CopyEdit
    function infinite() {
      return infinite();
    }
    infinite(); // ❌ Stack Overflow
    
    ```
    

---

### **2. Event Loop**

**🧠 Definition:**

The **Event Loop** allows JavaScript to perform non-blocking operations by offloading tasks like web API calls (e.g., `setTimeout`, `fetch`) to the browser, and handling them once the **Call Stack** is empty.

---

### **📌 How it works:**

1. Synchronous code runs first (on the Call Stack).
2. Async tasks (e.g., `setTimeout`, promises) are pushed to the Web APIs.
3. Once done, their callbacks go to the **Task Queue** (or Microtask Queue for promises).
4. Event Loop checks if the Call Stack is empty and moves the next task from the queue to the stack.

---

### **📌 Example:**

```jsx
javascript
CopyEdit
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 0);

Promise.resolve().then(() => {
  console.log("Promise");
});

console.log("End");

```

**Output:**

```
sql
CopyEdit
Start
End
Promise
Timeout

```

**Explanation:**

- `console.log("Start")` and `console.log("End")` → synchronous, runs first.
- `setTimeout(..., 0)` → moved to **Web API**, then **Task Queue**.
- `Promise.then()` → microtask → runs **before** tasks in Task Queue.

---

### ✅ What to do:

- Understand microtasks (e.g., promises) vs. macrotasks (e.g., `setTimeout`).
- Use the event loop knowledge to debug delays in async code.

---

### ❌ What not to do:

- ❌ Don’t assume `setTimeout(..., 0)` will run immediately—it waits for the stack to clear.
- ❌ Don’t block the main thread with long-running synchronous code.

---

### **🧠 Visual Analogy:**

- 🧠 **Call Stack**: The chef cooking one order at a time.
- 📥 **Web APIs**: The kitchen staff prepping ingredients.
- 📤 **Task Queue**: The waiter bringing food only after the chef is free.
- 🔁 **Event Loop**: The manager checking when the chef is free to start the next task.

---

**📚 Want to learn more?**

- 📘 *You Don’t Know JS (Async & Performance)* – Chapter 1: Asynchrony: Now & Later
- 📘 *Eloquent JavaScript* – Chapter 11: Asynchronous Programming
- 🌐 javascript.info – “Event loop”

---

## 3. Functional Programming Principles

---

### **🧠 Definition:**

**Functional Programming (FP)** is a programming paradigm where:

- Functions are treated as **first-class citizens** (can be assigned to variables, passed as arguments, or returned from other functions),
- **Immutability** is encouraged (don’t change data directly),
- **Pure functions** are preferred (same input always returns same output with no side effects),
- Code is often written using **higher-order functions**, composition, and declarative style.

---

### **📌 Key Principles & Examples:**

---

### **1. Pure Functions**

**Definition:**

A function is **pure** if it:

- Doesn’t change any external state,
- Returns the same output for the same input.

```jsx
javascript
CopyEdit
// Pure Function
function add(a, b) {
  return a + b;
}

// Impure Function (changes external state)
let total = 0;
function addToTotal(value) {
  total += value;  // ❌ Side effect
}

```

✅ What to do:

- Write predictable and testable functions.

❌ What not to do:

- ❌ Don’t rely on or modify external variables inside your functions.

---

### **2. Immutability**

**Definition:**

Don’t modify objects or arrays directly. Instead, create and return new ones.

```jsx
javascript
CopyEdit
// Bad: mutates the original array
let nums = [1, 2, 3];
nums.push(4);

// Good: returns a new array
let newNums = [...nums, 4];

```

✅ What to do:

- Use `map`, `filter`, `reduce`, and spread/rest syntax.

❌ What not to do:

- ❌ Avoid mutating arrays/objects with `push`, `splice`, etc.

---

### **3. First-Class Functions**

**Definition:**

Functions in JavaScript can be:

- Assigned to variables,
- Passed as arguments,
- Returned from other functions.

```jsx
javascript
CopyEdit
const greet = () => "Hello";

function executor(fn) {
  return fn();
}

console.log(executor(greet));  // Output: Hello

```

---

### **4. Higher-Order Functions (HOFs)**

**Definition:**

A **Higher-Order Function** is a function that:

- Takes another function as an argument,
- Returns a function.

```jsx
javascript
CopyEdit
function multiplier(factor) {
  return function(x) {
    return x * factor;
  };
}

const double = multiplier(2);
console.log(double(5)); // Output: 10

```

---

### **5. Declarative vs Imperative Style**

**Imperative:**

```jsx
javascript
CopyEdit
let result = [];
for (let i = 0; i < nums.length; i++) {
  result.push(nums[i] * 2);
}

```

**Declarative:**

```jsx
javascript
CopyEdit
const result = nums.map(n => n * 2);

```

✅ What to do:

- Prefer **declarative** code using array methods and composition.

---

### **6. Function Composition**

**Definition:**

Combining simple functions to build complex ones.

```jsx
javascript
CopyEdit
const add5 = x => x + 5;
const double = x => x * 2;

const composed = x => double(add5(x));
console.log(composed(10)); // Output: 30

```

---

### ✅ What to do:

- Write small, pure functions.
- Use HOFs like `.map()`, `.filter()`, `.reduce()`.
- Favor immutability and data transformation.

### ❌ What not to do:

- ❌ Avoid side effects (like modifying global variables or DOM in functions).
- ❌ Don’t mutate input parameters.

---

### **📚 Want to learn more?**

- 📘 *You Don’t Know JS (Scope & Closures + Async & Performance)* – touches on purity and first-class functions
- 📘 *Eloquent JavaScript* – Chapter 5: Higher-order functions
- 🌐 javascript.info – “First-class functions”

---

## 4. Modules (import/export)

---

### **🧠 Definition:**

**JavaScript Modules** allow you to organize code into separate files, exporting and importing variables, functions, classes, etc. This helps avoid global scope pollution and makes code easier to maintain and reuse.

---

### **📦 Syntax:**

### **Exporting (in file: `math.js`)**

```jsx
javascript
CopyEdit
// Named exports
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;

// Default export
const multiply = (a, b) => a * b;
export default multiply;

```

### **Importing (in file: `app.js`)**

```jsx
javascript
CopyEdit
// Import named exports
import { add, subtract } from './math.js';

// Import default export
import multiply from './math.js';

```

---

### **📌 Example:**

```jsx
javascript
CopyEdit
// file: greet.js
export function sayHello(name) {
  return `Hello, ${name}`;
}

```

```jsx
javascript
CopyEdit
// file: main.js
import { sayHello } from './greet.js';

console.log(sayHello("Alice"));  // Output: Hello, Alice

```

---

### ✅ What to do:

- Use named exports when exporting multiple functions/variables.
- Use default export for the main functionality of the file.
- Use ES Modules in modern projects (`.js` files with `"type": "module"` in `package.json` or `.mjs` extension).

---

### ❌ What not to do:

- ❌ Don’t mix default and named imports in confusing ways.
- ❌ Don’t forget the relative path (`./`) when importing local modules.
- ❌ Don’t try to use ES Modules without proper setup in environments that require CommonJS (like older Node.js versions without config).

---

### 🆚 Named vs Default Export:

| Feature | Named Export | Default Export |
| --- | --- | --- |
| Syntax | `export const foo = ...` | `export default foo` |
| Import Syntax | `import { foo }` | `import foo` |
| Import Name | Must match exported name | Can use any name |
| Quantity | Multiple per file | Only one per file |

---

### **📚 Want to learn more?**

- 📘 *Eloquent JavaScript* – Chapter 10: Modules
- 🌐 javascript.info – “Modules”
- 📘 *You Don’t Know JS* – ES6 & Beyond: Chapter 5 touches on modules (advanced view)

---

## 5. Memory Management

---

### **🧠 Definition:**

**Memory management** is the process of allocating and freeing memory in your application so that it runs efficiently and doesn’t consume more resources than necessary. In JavaScript, most of this is **automatic**, thanks to **Garbage Collection**.

---

### **📌 How It Works:**

JavaScript uses a **Garbage Collector (GC)** — primarily based on **mark-and-sweep algorithm**.

### **Mark-and-Sweep:**

1. The engine “marks” all values that are still being used (i.e., **reachable**).
2. It “sweeps” away the rest (unreachable or unused memory).

---

### **📦 Types of Memory:**

1. **Stack Memory:**
    - Stores **primitive values** (number, string, boolean, null, undefined, symbol, bigint).
    - Fast access.
2. **Heap Memory:**
    - Stores **objects**, **arrays**, and **functions**.
    - Used for dynamic memory allocation.

---

### **💡 Example:**

```jsx
javascript
CopyEdit
function createUser() {
  const name = "Alice";        // Stored in stack
  const user = { age: 25 };    // Object stored in heap
  return user;
}

```

Here:

- `"Alice"` is a primitive → stack.
- `{ age: 25 }` is an object → heap.

---

### ✅ What to do:

- ✅ Nullify references when no longer needed:
    
    ```jsx
    javascript
    CopyEdit
    let data = { /* large object */ };
    data = null;  // Helps GC clean up
    
    ```
    
- ✅ Be careful with closures that retain unnecessary references.
- ✅ Use event listeners wisely (remove when not needed).

---

### ❌ What not to do:

- ❌ Avoid global variables (they stay in memory till the page is closed).
- ❌ Don’t create circular references:
    
    ```jsx
    javascript
    CopyEdit
    let a = {};
    let b = {};
    a.ref = b;
    b.ref = a;  // ❌ Can confuse GC in some cases
    
    ```
    
- ❌ Avoid memory leaks from DOM elements no longer in the document:
    
    ```jsx
    javascript
    CopyEdit
    const el = document.getElementById("myDiv");
    el.onclick = () => alert("Clicked"); // if el is removed later, listener may stay
    
    ```
    

---

### 🧠 Common Causes of Memory Leaks:

- Forgotten timers (`setInterval`, `setTimeout`)
- Detached DOM nodes with event handlers
- Unclosed WebSocket or open event listeners
- Massive in-memory data (logs, cache) not cleared

---

### 🧰 Tools to Monitor:

- **Chrome DevTools** → `Memory` tab
- **Performance Profiler** for heap snapshots
- **`console.memory`** in browser

---

### 📚 Want to learn more?

- 📘 *You Don’t Know JS: Scope & Closures* — talks about memory scope and lifetimes.
- 📘 *Eloquent JavaScript* – Chapter 4: Data Structures; touches on memory indirectly.
- 🌐 javascript.info – “Garbage Collection”

---

## 6. Web APIs & DOM Events

---

### **🧠 Definition:**

**Web APIs** are built-in browser interfaces (not part of JavaScript itself) that allow you to interact with things like the DOM, HTTP requests, timers, geolocation, storage, and more.

**DOM Events** are signals that something has happened in the browser (e.g., click, hover, input, load). JavaScript can listen to these and react accordingly.

---

### **🌐 Examples of Web APIs:**

- **DOM API** – `document.querySelector`, `element.classList`
- **Fetch API** – `fetch()`
- **Timers API** – `setTimeout`, `setInterval`
- **Geolocation API** – `navigator.geolocation.getCurrentPosition()`
- **Storage API** – `localStorage`, `sessionStorage`

---

### **📦 Basic DOM Events Syntax:**

```jsx
javascript
CopyEdit
// HTML
<button id="clickMe">Click Me</button>

// JS
const btn = document.getElementById('clickMe');
btn.addEventListener('click', () => {
  alert('Button was clicked!');
});

```

---

### **📌 Example: Input + Event**

```html
html
CopyEdit
<input type="text" id="nameInput" placeholder="Enter your name" />
<script>
  const input = document.getElementById('nameInput');
  input.addEventListener('input', (e) => {
    console.log('User typed:', e.target.value);
  });
</script>

```

---

### ✅ What to do:

- ✅ Use `addEventListener` instead of inline `onclick` in HTML for separation of concerns.
- ✅ Remove event listeners when no longer needed to avoid memory leaks.
- ✅ Use event delegation for dynamic elements:
    
    ```jsx
    javascript
    CopyEdit
    document.body.addEventListener('click', (e) => {
      if (e.target.matches('.dynamic-btn')) {
        // Handle dynamic button click
      }
    });
    
    ```
    

---

### ❌ What not to do:

- ❌ Don’t manipulate DOM excessively inside loops (can slow down UI).
- ❌ Avoid deeply nested event handlers; use delegation.
- ❌ Avoid inline JavaScript (`<button onclick="alert('Hi')">`) in production code.

---

### 📚 Want to learn more?

- 📘 *Eloquent JavaScript* – Chapter 14: The Document Object Model
- 🌐 javascript.info – “Browser Environment”
- 📘 *You Don’t Know JS* – Scope & Closures (for how functions behave inside handlers)

---

## 7. Debouncing & Throttling

---

### **🧠 Definition:**

### **Debouncing**

A technique that delays function execution until after a certain time has passed **since the last event**.

> Used to limit the rate at which a function gets called, typically for events like keyup, resize, or input.
> 

### **Throttling**

A technique that ensures a function is called at most **once every X milliseconds**, **regardless of how often** the event is triggered.

> Useful for things like scroll, mousemove, or window resize events.
> 

---

### **📦 Syntax & Examples:**

### Debounce:

```jsx
javascript
CopyEdit
function debounce(func, delay) {
  let timeout;
  return function (...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => func.apply(this, args), delay);
  };
}

const logInput = debounce(() => {
  console.log("Input event processed");
}, 500);

document.getElementById("search").addEventListener("input", logInput);

```

### Throttle:

```jsx
javascript
CopyEdit
function throttle(func, limit) {
  let inThrottle;
  return function (...args) {
    if (!inThrottle) {
      func.apply(this, args);
      inThrottle = true;
      setTimeout(() => (inThrottle = false), limit);
    }
  };
}

const logScroll = throttle(() => {
  console.log("Scroll event processed");
}, 1000);

window.addEventListener("scroll", logScroll);

```

---

### ✅ What to do:

- ✅ Use **debounce** when you want to delay execution until the user is done (e.g., search input).
- ✅ Use **throttle** when you want a function to run at regular intervals during high-frequency events (e.g., scroll handler).
- ✅ Test performance using DevTools when applying these techniques.

---

### ❌ What not to do:

- ❌ Don’t use raw event listeners on performance-heavy actions like scroll or resize without throttle/debounce.
- ❌ Don’t debounce every event without understanding its effect (e.g., form validation on blur should not be debounced).
- ❌ Avoid anonymous inline debounce/throttle wrappers in JSX or listeners — hard to remove later.

---

### 🧠 When to use:

| Scenario | Use |
| --- | --- |
| User typing search | Debounce |
| Window resizing | Throttle |
| Auto-saving form data | Debounce |
| Infinite scroll | Throttle |
| Mouse move tracking | Throttle |

---

### 📚 Want to learn more?

- 🌐 javascript.info – Event loop section
- 📘 *Eloquent JavaScript* – Chapter 15: Handling Events
- 📘 *You Don’t Know JS* – Scope & Closures (context around function calls and timing)

---

## 8. Design Patterns in JavaScript

---

### **🧠 Definition:**

A **design pattern** is a general, reusable solution to a common problem in software design. It’s not code, but a template for solving problems that can be adapted to different situations.

JavaScript supports several classic **object-oriented** and **functional** design patterns.

---

### **📦 Common JS Design Patterns:**

---

### 1. **Module Pattern**

Encapsulates private variables and exposes only the parts you need.

```jsx
javascript
CopyEdit
const Counter = (function () {
  let count = 0;
  return {
    increment: () => ++count,
    getCount: () => count
  };
})();

Counter.increment(); // 1
Counter.getCount();  // 1

```

✅ Use to encapsulate logic

❌ Don’t overuse IIFEs in modern code — prefer ES6 modules

---

### 2. **Factory Pattern**

Creates objects without specifying the exact class.

```jsx
javascript
CopyEdit
function createUser(name, role) {
  return {
    name,
    role,
    sayHi() {
      console.log(`Hi, I'm ${this.name}`);
    }
  };
}

const user = createUser("Alice", "Admin");

```

✅ Great for creating similar objects

❌ Not ideal when object types are complex or heavily subclassed

---

### 3. **Singleton Pattern**

Ensures only one instance of an object exists.

```jsx
javascript
CopyEdit
const Singleton = (function () {
  let instance;
  function createInstance() {
    return { id: Math.random() };
  }
  return {
    getInstance: function () {
      if (!instance) instance = createInstance();
      return instance;
    }
  };
})();

const a = Singleton.getInstance();
const b = Singleton.getInstance();
console.log(a === b); // true

```

✅ Good for global config, state management

❌ Avoid when multiple instances might be needed (can limit flexibility)

---

### 4. **Observer Pattern**

Allows a subject to notify multiple observers when a state changes.

```jsx
javascript
CopyEdit
class Subject {
  constructor() {
    this.observers = [];
  }
  subscribe(observer) {
    this.observers.push(observer);
  }
  notify(data) {
    this.observers.forEach(fn => fn(data));
  }
}

const news = new Subject();
news.subscribe(data => console.log("News:", data));
news.notify("New update available!");

```

✅ Great for event-driven architectures

❌ Can get messy without unsubscribe mechanisms

---

### 5. **Prototype Pattern**

Use JavaScript’s built-in prototype chain to share methods across instances.

```jsx
javascript
CopyEdit
function Animal(name) {
  this.name = name;
}
Animal.prototype.speak = function () {
  console.log(`${this.name} makes a noise.`);
};

const dog = new Animal("Dog");
dog.speak(); // Dog makes a noise.

```

✅ Memory-efficient for shared methods

❌ Tricky syntax and behavior for newcomers

---

### ✅ What to do:

- ✅ Use design patterns **when needed**, not blindly.
- ✅ Know the pros and cons of each pattern.
- ✅ Modularize and reuse code using patterns like Module and Factory.

---

### ❌ What not to do:

- ❌ Don’t force design patterns where a simple function or module would do.
- ❌ Avoid tightly coupling code — use Observer and Factory to keep things decoupled.
- ❌ Don’t forget maintainability — too many patterns = spaghetti code.

---

### 📚 Want to learn more?

- 📘 *You Don’t Know JS* – Objects & Classes section
- 📘 *Eloquent JavaScript* – Chapter 6: The Secret Life of Objects
- 🌐 javascript.info – OOP & Prototypes section
