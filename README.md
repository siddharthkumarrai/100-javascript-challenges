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

console.log(x: ${x}, y: ${y}, z: ${z}, n: ${n});
```
### 🗳️ Quick Vote:

**Question:** What will be logged to the console?

**Options:**
- A) `x: 102, y: 100, z: 102, n: 102`
- B) `x: 102, y: 100, z: 103, n: 103` 
- C) `x: 101, y: 100, z: 102, n: 103`
- D) `x: 103, y: 100, z: 103, n: 103`

<details>
<summary>💡 Click to see solution</summary>

**Answer: B** `x: 102, y: 100, z: 103, n: 103`

**Explanation:**
1. `let x = 100;` → x = 100
2. `let y = x++;` → y gets current value of x (100), then x increments to 101
3. `let z = ++x;` → x increments to 102 first, then z gets this value (102)
4. `let n = (x == y) ? z++ : ++z;` → x(102) ≠ y(100), so execute `++z`
   - z increments to 103 first, then n gets this value (103)

**Final values:** x=102, y=100, z=103, n=103

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

**Answer: C** 

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
