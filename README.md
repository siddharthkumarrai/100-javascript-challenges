# 🚀 100 JavaScript Challenges
A comprehensive collection of 100 JavaScript challenges designed to test your understanding of core concepts, tricky behaviors, and advanced patterns.

## 📚 Table of Contents
- [How to Use](#how-to-use)
- [Difficulty Levels](#difficulty-levels)
- [Challenge Categories](#challenge-categories)
- [Challenges](#challenges)
- [Contributing](#contributing)

## 🎯 How to Use
Each challenge follows this format:
1. **Quiz**: A code snippet with a question
2. **Options**: Multiple choice answers (where applicable)
3. **Solution**: Detailed explanation with the correct answer
4. **Concepts**: Key JavaScript concepts covered

## 📊 Difficulty Levels
- 🟢 **Beginner** (1-25): Basic syntax and concepts
- 🟡 **Intermediate** (26-70): Tricky behaviors and patterns  
- 🔴 **Advanced** (71-100): Complex scenarios and edge cases

## 🏷️ Challenge Categories
- **Variables & Operators** (1-15)
- **Functions & Scope** (16-30)
- **Objects & Arrays** (31-45)
- **Asynchronous JavaScript** (46-60)
- **ES6+ Features** (61-75)
- **Advanced Concepts** (76-100)

---

## 🧩 Challenges

### Challenge #1: Increment Operators 🟢

**Quiz:**
```javascript
let x = 100;
let y = x++;
let z = ++x;
let n = (x == y) ? z++ : ++z;
```

### 🗳️ Quick Vote:
**Question:** What is the value of "n"?

**Options:**
- A) `100`
- B) `101`
- C) `102`
- D) `103`

<details>
<summary>💡 Click to see solution</summary>

**Answer: D** `103`

**Explanation:**
1. `let x = 100;` → x = 100
2. `let y = x++;` → y gets current value of x (100), then x increments to 101
3. `let z = ++x;` → x increments to 102 first, then z gets this value (102)
4. `let n = (x == y) ? z++ : ++z;` → x(102) ≠ y(100), so execute `++z`
   - z increments to 103 first, then n gets this value (103)

**Final values:** x=102, y=100, z=102, n=103

**Concepts Covered:**
- Post-increment operator (`x++`)
- Pre-increment operator (`++x`)
- Ternary operator
- Operator precedence

</details>

---

### Challenge #2: Boolean Constructor 🟢

**Quiz:**
```javascript
const f = new Boolean(false);

if (f) {
console.log(1);
} else {
console.log(2);
}

console.log(typeof f);
```

### 🗳️ Quick Vote:
**Question:** What will be logged to the console?

**Options:**
- A) `1, boolean`
- B) `2, boolean`
- C) `1, object`
- D) `2, object`

<details>
<summary>💡 Click to see solution</summary>

**Answer: C** `1, object`

**Explanation:**
1. `const f = new Boolean(false);` → Creates a Boolean object wrapper, not a primitive boolean
2. Boolean objects are always truthy in JavaScript, regardless of the value they wrap
3. `if (f)` → Since f is an object (truthy), the condition evaluates to true, so `console.log(1)` executes
4. `console.log(typeof f);` → The typeof operator returns "object" for Boolean objects, not "boolean"

**Key Point:** `new Boolean(false)` creates an object that wraps the false value, but the object itself is truthy!

**Final output:** 

**Concepts Covered:**
- Boolean constructor vs primitive booleans
- Truthy/falsy values
- Object wrappers
- typeof operator behavior
- Difference between `Boolean(false)` and `new Boolean(false)`

</details>

---
### Challenge #3: Destructuring Assignment 🟢

**Quiz:**
```javascript
const obj = { x: 1, y: 2 };
let { x: a, y: b } = obj;
a = 2;
console.log(obj.x, obj.y);
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `1, 2`
- B) `2, 2`
- C) `TypeError`
- D) `ReferenceError`

<details>
<summary>💡 Click to see solution</summary>

**Answer: A** 

**Explanation:**
1. `const obj = { x: 1, y: 2 };` → Creates an object with properties x and y
2. `let { x: a, y: b } = obj;` → Destructuring assignment creates new variables `a` and `b` with values from `obj.x` and `obj.y`
3. `a = 2;` → Changes the value of variable `a`, but does NOT affect `obj.x`
4. `console.log(obj.x, obj.y);` → The original object remains unchanged

**Key Point:** Destructuring creates new variables; modifying them doesn't affect the original object!

**Final output:** 

**Concepts Covered:**
- Destructuring assignment
- Object properties vs variables
- Variable aliasing in destructuring
- Object immutability concepts

</details>

---

### Challenge #4: Hoisting and Temporal Dead Zone 🟡

**Quiz:**
```javascript
let elf = 'Estel';

function lapland(params) {
console.log(elf);
let elf = 'Arwen';
}

lapland();
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `undefined`
- B) `ReferenceError`
- C) `Arwen`
- D) `Estel`

<details>
<summary>💡 Click to see solution</summary>

**Answer: B** 

**Explanation:**
1. The function `lapland` has a local `let elf = 'Arwen';` declaration
2. Due to hoisting, the `let elf` declaration is hoisted to the top of the function scope
3. However, `let` variables are in the "Temporal Dead Zone" before their declaration line
4. `console.log(elf);` tries to access `elf` before it's initialized, causing a ReferenceError
5. The global `elf = 'Estel'` is shadowed by the local declaration

**Key Point:** `let` and `const` are hoisted but remain uninitialized until their declaration line!

**Final output:** 
ReferenceError: Cannot access 'elf' before initialization

**Concepts Covered:**
- Hoisting behavior of `let` vs `var`
- Temporal Dead Zone
- Variable shadowing
- Function scope vs block scope

</details>

---

### Challenge #5: Object.hasOwn Method 🟢

**Quiz:**
```javascript
const obj = {};
obj.value = undefined;
console.log(Object.hasOwn(obj, 'value'));
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `undefined`
- B) `false`
- C) `true`
- D) `{}`

<details>
<summary>💡 Click to see solution</summary>

**Answer: C**

**Explanation:**
1. `const obj = {};` → Creates an empty object
2. `obj.value = undefined;` → Adds a property 'value' with the value `undefined` to the object
3. `Object.hasOwn(obj, 'value')` → Checks if the object has its own property named 'value'
4. Even though the property value is `undefined`, the property itself exists on the object

**Key Point:** `Object.hasOwn()` checks for property existence, not the property's value!

**Final output:** 
true

**Concepts Covered:**
- Object.hasOwn() method
- Property existence vs property value
- undefined as a valid property value
- Own properties vs inherited properties

</details>

---

### Challenge #6: setTimeout and Function References 🟡

**Quiz:**
```javascript
let foo = function () {
console.log(1);
};

setTimeout(foo, 1000);

foo = function () {
console.log(2);
};
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `1`
- B) `2`
- C) `Error`

<details>
<summary>💡 Click to see solution</summary>

**Answer: A**

**Explanation:**
1. `let foo = function () { console.log(1); };` → `foo` points to the first function
2. `setTimeout(foo, 1000);` → setTimeout captures a reference to the current function (the one that logs 1)
3. `foo = function () { console.log(2); };` → `foo` now points to a different function, but setTimeout still has the reference to the original function
4. After 1000ms, setTimeout executes the original function that logs 1

**Key Point:** setTimeout captures the function reference at the time it's called, not when it executes!

**Final output (after 1 second):** 
1

**Concepts Covered:**
- Function references vs function calls
- setTimeout behavior
- Variable reassignment
- Closure and lexical scoping

</details>

---
### Challenge #7: String Comparison 🟢

**Quiz:**
```javascript
console.log("9" > "19");
console.log("09" > "19");
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `true, true`
- B) `false, true`
- C) `true, false`
- D) `false, false`

<details>
<summary>💡 Click to see solution</summary>

**Answer: C** `true, false`

**Explanation:**
1. `console.log("9" > "19");` → String comparison is lexicographic (alphabetical)
   - "9" vs "19": First character "9" > "1", so result is `true`
2. `console.log("09" > "19");` → String comparison character by character
   - "09" vs "19": First character "0" < "1", so result is `false`

**Key Point:** String comparison in JavaScript is lexicographic, not numeric!

**Final output:** 
true
false


**Concepts Covered:**
- String comparison vs numeric comparison
- Lexicographic ordering
- Type coercion behavior
- Leading zeros in strings

</details>

---

### Challenge #8: Type Coercion and Operator Precedence 🟢

**Quiz:**
```javascript
console.log(1 + 2 + '1');
console.log('1' + 1 + 2);
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `112, 112`
- B) `121, 112`
- C) `31, 13`
- D) `31, 112`

<details>
<summary>💡 Click to see solution</summary>

**Answer: D** `31, 112`

**Explanation:**
1. `console.log(1 + 2 + '1');` → Left-to-right evaluation
   - `1 + 2` = `3` (numeric addition)
   - `3 + '1'` = `"31"` (string concatenation, 3 converts to "3")
2. `console.log('1' + 1 + 2);` → Left-to-right evaluation
   - `'1' + 1` = `"11"` (string concatenation, 1 converts to "1")
   - `"11" + 2` = `"112"` (string concatenation, 2 converts to "2")

**Key Point:** The `+` operator is left-associative; when one operand is a string, it becomes string concatenation!

**Final output:** 
31
112


**Concepts Covered:**
- Type coercion with + operator
- Operator associativity
- String concatenation vs numeric addition
- Left-to-right evaluation

</details>

---

### Challenge #9: Function Expression vs Function Declaration 🟡

**Quiz:**
```javascript
var bar = function foo() {};
console.log(bar === foo);
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `true`
- B) `false`
- C) `ReferenceError`

<details>
<summary>💡 Click to see solution</summary>

**Answer: C** `ReferenceError`

**Explanation:**
1. `var bar = function foo() {};` → Creates a named function expression
2. The function is assigned to variable `bar`
3. The name `foo` is only available inside the function itself, not in the outer scope
4. `console.log(bar === foo);` → Tries to access `foo` in outer scope, which doesn't exist
5. This throws a ReferenceError because `foo` is not defined in the current scope

**Key Point:** In named function expressions, the function name is only accessible within the function's own scope!

**Final output:** 
ReferenceError: foo is not defined


**Concepts Covered:**
- Named function expressions
- Function scope and accessibility
- Variable hoisting vs function name scope
- ReferenceError vs other error types

</details>

---

### Challenge #10: setTimeout and Object Property Deletion 🟡

**Quiz:**
```javascript
let obj = {
timeoutId: setTimeout(() => {
console.log('hi');
}, 1000)
};

delete obj.timeoutId;
obj = null;
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `No error & No log`
- B) `hi`
- C) `Error`

<details>
<summary>💡 Click to see solution</summary>

**Answer: B** `hi`

**Explanation:**
1. `setTimeout(() => { console.log('hi'); }, 1000)` → Schedules a function to run after 1000ms
2. The timeout ID is stored in `obj.timeoutId`
3. `delete obj.timeoutId;` → Removes the property, but the timeout is already scheduled in the browser's timer queue
4. `obj = null;` → Removes the reference to the object, but doesn't affect the scheduled timeout
5. After 1000ms, the scheduled function still executes because setTimeout maintains its own reference

**Key Point:** Once setTimeout is called, it's managed by the browser's event loop independently of your object references!

**Final output (after 1 second):** 
hi

**Concepts Covered:**
- setTimeout and event loop
- Object property deletion
- Memory management and references
- Asynchronous JavaScript execution

</details>

---
### Challenge #11: Symbols and JSON Serialization 🟡

**Quiz:**
```javascript
const myObject = {};
const key = Symbol('key');
myObject[key] = 'value';
console.log(myObject[Symbol('key')]);
console.log(JSON.stringify(myObject));
```


### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `value, {}`
- B) `undefined, {}`
- C) `value, {"key": "value"}`
- D) `value, { Symbol("key"): "value" }`

<details>
<summary>💡 Click to see solution</summary>

**Answer: B** `undefined, {}`

**Explanation:**
1. `const key = Symbol('key');` → Creates a unique symbol
2. `myObject[key] = 'value';` → Sets property using the symbol as key
3. `console.log(myObject[Symbol('key')]);` → Creates a NEW symbol with same description, but it's different from the original
4. Since each Symbol() call creates a unique symbol, accessing with `Symbol('key')` returns `undefined`
5. `JSON.stringify(myObject)` → Symbol properties are ignored during JSON serialization

**Key Point:** Each `Symbol()` call creates a unique symbol, even with the same description!

**Final output:** 
undefined
{}


**Concepts Covered:**
- Symbol uniqueness
- Symbol as object keys
- JSON.stringify behavior with symbols
- Symbol registry vs local symbols

</details>

---

### Challenge #12: Object.setPrototypeOf 🟡

**Quiz:**
```javascript
let x = {
a: 1,
b: 2
};
let y = {
b: 3,
c: 4
};
Object.setPrototypeOf(x, y);
console.log(x.b);
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `1`
- B) `2`
- C) `3`
- D) `4`

<details>
<summary>💡 Click to see solution</summary>

**Answer: B** `2`

**Explanation:**
1. Object `x` has properties `a: 1` and `b: 2`
2. Object `y` has properties `b: 3` and `c: 4`
3. `Object.setPrototypeOf(x, y);` → Sets `y` as the prototype of `x`
4. `console.log(x.b);` → Looks for property `b` on `x` first
5. Since `x` has its own `b` property with value `2`, it doesn't look up the prototype chain
6. Own properties take precedence over inherited properties

**Key Point:** Own properties shadow prototype properties with the same name!

**Final output:** 
2


**Concepts Covered:**
- Prototype chain
- Object.setPrototypeOf()
- Property shadowing
- Own properties vs inherited properties

</details>

---

### Challenge #13: Try-Catch-Finally and Delete Operator 🟡

**Quiz:**
```javascript
foo = 2;

try {
foo = 2 / 0;
} catch (e) {
delete foo;
} finally {
foo = foo * -1;
}

console.log(foo);
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `Infinity`
- B) `-Infinity`
- C) `Error`
- D) `undefined`

<details>
<summary>💡 Click to see solution</summary>

**Answer: B** `-Infinity`

**Explanation:**
1. `foo = 2;` → Creates global variable `foo` with value `2`
2. `try { foo = 2 / 0; }` → Division by zero results in `Infinity`, no error thrown
3. `catch (e)` block is NOT executed because no error was thrown
4. `finally { foo = foo * -1; }` → Always executes, `foo` is `Infinity`, so `Infinity * -1 = -Infinity`
5. `console.log(foo);` → Outputs `-Infinity`

**Key Point:** Division by zero in JavaScript returns `Infinity`, not an error!

**Final output:** 
-Infinity

**Concepts Covered:**
- Try-catch-finally execution flow
- Division by zero behavior
- Infinity arithmetic
- When catch blocks execute

</details>

---

### Challenge #14: This Context in Function Calls 🟡

**Quiz:**
```javascript
var obj = {
x: 2,
fun: function() {
console.log(this.x);
},
};

obj.fun();
new obj.fun();
```

### 🗳️ Quick Vote:
**Question:** What is the output?

**Options:**
- A) `2, 2`
- B) `undefined, 2`
- C) `2, {}` 
- D) `undefined, {}`

<details>
<summary>💡 Click to see solution</summary>

**Answer: C** `2, undefined`

**Explanation:**
1. `obj.fun();` → Method call: `this` refers to `obj`, so `this.x` is `2`
2. `new obj.fun();` → Constructor call: `this` refers to a new empty object `{}`
3. The new object doesn't have an `x` property, so `this.x` is `undefined`
4. When using `new`, the function becomes a constructor and `this` points to the newly created instance

**Key Point:** The `new` operator changes the `this` context to a new object instance!

**Final output:** 
2
undefined

**Concepts Covered:**
- Method vs constructor invocation
- `this` binding rules
- `new` operator behavior
- Object method context

</details>

---
