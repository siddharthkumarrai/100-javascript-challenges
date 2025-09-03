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
