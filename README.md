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

### ❓ What will be logged to the console?

**Click to vote (updates automatically):**

<table>
  <tr>
    <td><strong>Option A</strong></td>
    <td><code>x: 102, y: 100, z: 102, n: 102</code></td>
    <td>
      <a href="https://github.com/username/repo/issues/new?title=Vote%20Challenge%201%20Option%20A&body=Voting%20for%20Option%20A&labels=vote,challenge-1,option-a">
        <img src="https://img.shields.io/badge/👆%20VOTE-A-blue?style=for-the-badge" alt="Vote A"/>
      </a>
    </td>
    <td>
      <img src="https://img.shields.io/github/issues-search/username/repo?query=label%3A%22vote%22%20label%3A%22challenge-1%22%20label%3A%22option-a%22&label=votes&color=blue" alt="A votes"/>
    </td>
  </tr>
  <tr>
    <td><strong>Option B</strong></td>
    <td><code>x: 102, y: 100, z: 103, n: 103</code></td>
    <td>
      <a href="https://github.com/username/repo/issues/new?title=Vote%20Challenge%201%20Option%20B&body=Voting%20for%20Option%20B&labels=vote,challenge-1,option-b">
        <img src="https://img.shields.io/badge/👆%20VOTE-B-green?style=for-the-badge" alt="Vote B"/>
      </a>
    </td>
    <td>
      <img src="https://img.shields.io/github/issues-search/username/repo?query=label%3A%22vote%22%20label%3A%22challenge-1%22%20label%3A%22option-b%22&label=votes&color=green" alt="B votes"/>
    </td>
  </tr>
  <tr>
    <td><strong>Option C</strong></td>
    <td><code>x: 101, y: 100, z: 102, n: 103</code></td>
    <td>
      <a href="https://github.com/username/repo/issues/new?title=Vote%20Challenge%201%20Option%20C&body=Voting%20for%20Option%20C&labels=vote,challenge-1,option-c">
        <img src="https://img.shields.io/badge/👆%20VOTE-C-orange?style=for-the-badge" alt="Vote C"/>
      </a>
    </td>
    <td>
      <img src="https://img.shields.io/github/issues-search/username/repo?query=label%3A%22vote%22%20label%3A%22challenge-1%22%20label%3A%22option-c%22&label=votes&color=orange" alt="C votes"/>
    </td>
  </tr>
  <tr>
    <td><strong>Option D</strong></td>
    <td><code>x: 103, y: 100, z: 103, n: 103</code></td>
    <td>
      <a href="https://github.com/username/repo/issues/new?title=Vote%20Challenge%201%20Option%20D&body=Voting%20for%20Option%20D&labels=vote,challenge-1,option-d">
        <img src="https://img.shields.io/badge/👆%20VOTE-D-red?style=for-the-badge" alt="Vote D"/>
      </a>
    </td>
    <td>
      <img src="https://img.shields.io/github/issues-search/username/repo?query=label%3A%22vote%22%20label%3A%22challenge-1%22%20label%3A%22option-d%22&label=votes&color=red" alt="D votes"/>
    </td>
  </tr>
</table>

### 📊 Live Results:
![Total Votes](https://img.shields.io/github/issues-search/username/repo?query=label%3A%22vote%22%20label%3A%22challenge-1%22&label=Total%20Votes&color=purple&style=for-the-badge)

<details>
<summary>💡 Show Solution</summary>

**Answer: B** `x: 102, y: 100, z: 103, n: 103`

**Explanation:**
1. `x = 100` initially  
2. `y = x++` → y gets 100, x becomes 101
3. `z = ++x` → x becomes 102, z gets 102
4. `(x == y)` is false (102 ≠ 100)
5. Execute `++z` → z becomes 103, n gets 103

</details>

