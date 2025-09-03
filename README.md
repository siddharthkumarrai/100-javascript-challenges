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

### Challenge #2: Variable Hoisting 🟢

**Quiz:**

```javascript
console.log(a);
var a = 5;
console.log(a);

console.log(b);
let b = 10;
```

**Question:** What will happen when this code runs?

**Options:**
- A) undefined, 5, ReferenceError
- B) ReferenceError, 5, undefined
- C) undefined, 5, undefined
- D) 5, 5, 10

<details>
<summary>💡 Click to see solution</summary>

**Answer: A** undefined, 5, ReferenceError

**Explanation:**
1. `var` declarations are hoisted and initialized with `undefined`
2. First `console.log(a)` prints `undefined`
3. After assignment, second `console.log(a)` prints `5`
4. `let` declarations are hoisted but not initialized (Temporal Dead Zone)
5. Accessing `b` before declaration throws `ReferenceError`

**Concepts Covered:**
- Variable hoisting
- Temporal Dead Zone
- Difference between `var` and `let`

</details>

---

### Challenge #3: This Binding 🟡

**Quiz:**
