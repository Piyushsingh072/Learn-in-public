# 🌙 EOD — DAY 1

## 🎯 Today's Goal

Restart DSA from the foundations and begin the **September → December 31 Winter Arc** with the goal of building genuine problem-solving ability, not just completing a syllabus.

---

## 📚 Topics Covered

* What is DSA?
* Data structures vs algorithms
* Input size `n`
* Time complexity
* `O(1)`
* `O(n)`
* `O(n²)`
* Space complexity
* `O(1)` space
* `O(n)` space
* Sequential vs nested loops
* Constants vs input-dependent work

---

## 🧠 What I Learned

### Data Structure

You correctly described it as:

> **How we organize data.**

Example: **Array**

### Algorithm

You correctly described it as:

> **Steps used to perform a certain task/problem.**

Example: **Linear Search**

### `n`

`n` represents the **size of the input**.

For an array containing 1,000 elements:

```text
n = 1000
```

### Time Complexity

You learned to think about **how the amount of work grows as `n` grows**, rather than actual execution time.

---

## 🔍 Starting Knowledge

You already had some basic understanding of:

* Arrays
* Algorithms
* Linear search
* The general idea of `O(n)`

But you needed to strengthen the reasoning behind complexity rather than simply recognizing complexity labels.

---

# 📈 Ending Knowledge

You successfully reasoned through:

### `O(1)`

```cpp
cout << arr[0];
```

One fixed operation regardless of `n`.

### `O(n)`

```cpp
for (int i = 0; i < n; i++)
```

Work grows proportionally with `n`.

### `O(n²)`

```cpp
for (int i = 0; i < n; i++)
    for (int j = 0; j < n; j++)
```

`n × n` operations.

### `O(n)` with two separate loops

You correctly understood:

```text
O(n) + O(n)
= O(2n)
= O(n)
```

### Space complexity

You correctly distinguished:

```cpp
int sum;
```

→ `O(1)` extra space

from:

```cpp
int temp[n];
```

→ `O(n)` extra space.

---

# 🔄 Learning Loops

### Complexity distinction

**Explanation → Your reasoning → Mistake → Correction → Re-test → Correct**

You initially made one important misconception:

> A loop printing `arr[0]` repeatedly could be `O(1)` because the accessed element doesn't change.

Correction:

> The **operation** is `O(1)`, but if the loop performs it `n` times, the **total algorithm is `O(n)`**.

You then successfully understood the distinction.

### Fixed loop vs input-dependent loop

You initially classified a loop running exactly 10 times as `O(n)`.

Correction:

> A fixed number of iterations is constant, regardless of input size.

You then correctly identified even **1,000,000 fixed iterations** as `O(1)`.

**Learning loop completed successfully.**

---

# ❌ Mistakes & Corrections

| Mistake                                                        | Correction                             | Lesson                                                         |
| -------------------------------------------------------------- | -------------------------------------- | -------------------------------------------------------------- |
| `for` loop printing `arr[0]` → thought `O(1)`                  | Loop still executes `n` times → `O(n)` | Analyze total repetitions, not just the operation              |
| Fixed 10-iteration loop → thought `O(n)`                       | 10 is constant → `O(1)`                | `n` means input size, not "number of iterations" automatically |
| `temp[i]` assignment thought to be the reason for `O(n)` space | `temp[n]` itself creates `n` storage   | Focus on memory allocated, not updates                         |

### Recurring weakness identified

**Be careful not to equate "loop" automatically with `O(n)`.**

Ask:

> **Does the number of iterations actually depend on `n`?**

---

# 🧩 Concept Cards

## CONCEPT: `O(1)`

**Definition:** Constant work regardless of input size.

**Mental Model:**
`n` grows → work stays roughly the same.

**Example:**

```cpp
cout << arr[0];
```

**Time:** `O(1)`

**Space:** `O(1)` if only fixed variables are used.

**Mastery Test:** Identify constant operations even when they appear inside other structures.

---

## CONCEPT: `O(n)`

**Definition:** Work grows proportionally with input size.

**Mental Model:**

```text
n doubles → roughly 2× the work
```

**Example:**

```cpp
for (int i = 0; i < n; i++)
```

**Time:** `O(n)`

**Important pattern:**

```text
O(n) + O(n) → O(n)
```

---

## CONCEPT: `O(n²)`

**Definition:** Work grows approximately with the square of input size.

**Mental Model:**

> For every outer iteration, perform `n` inner iterations.

**Example:**

```cpp
for (int i = 0; i < n; i++)
    for (int j = 0; j < n; j++)
```

**Time:** `O(n²)`

**Pattern:**

```text
n × n = n²
```

---

## CONCEPT: Space Complexity

**Definition:** How much **extra memory** an algorithm requires as input grows.

**Mental Model:**

> Are we creating more storage as `n` increases?

```text
fixed variables → O(1)
array of size n → O(n)
```

---

# 🧪 Problems & Attempts

### Problem 1 — Single array access

**Problem:** Analyze `cout << arr[0];`

**Attempt:** Correctly identified `O(1)`.

**Result:** ✅

**Independent?:** Yes.

---

### Problem 2 — Single `n` loop

**Problem:** Print every element.

**Attempt:** Correctly identified `O(n)`.

**Result:** ✅

**Independent?:** Yes.

---

### Problem 3 — `n` loop repeatedly printing `arr[0]`

**Attempt:** Initially `O(1)`.

**Correction:** The loop still executes `n` times.

**Final Result:** `O(n)`.

**Independent?:** Improved after correction.

---

### Problem 4 — Fixed 10-iteration loop

**Attempt:** Initially `O(n)`.

**Correction:** 10 is independent of input size.

**Final Result:** `O(1)`.

**Independent?:** Yes after correction.

---

### Problem 5 — Nested loops

**Attempt:** Correctly reasoned `n × n = n²`.

**Final Result:** `O(n²)`.

**Independent?:** Yes.

---

### Problem 6 — Constant space

**Attempt:** Correctly identified fixed variables as `O(1)` space.

**Result:** ✅

---

### Problem 7 — Additional `temp[n]` array

**Attempt:** Correctly identified `O(n)` space.

**Result:** ✅

---

### Problem 8 — Two loops + temporary array

**Attempt:** Correctly identified:

```text
Time  → O(n)
Space → O(n)
```

**Result:** ✅

**Independent?:** Yes.

---

# 🏆 Evidence of Progress

The strongest improvement today wasn't memorizing Big-O labels.

You started distinguishing:

> **operation cost** vs **number of repetitions**

and:

> **fixed amount of work** vs **input-dependent work**

You also correctly learned that **two separate `O(n)` loops don't automatically become `O(n²)`**.

---

# 🔴 Remaining Weaknesses

### 1. `O(log n)` — Not learned yet

We stopped before covering logarithmic complexity.

### 2. Complexity of more complicated loops

We haven't yet tested:

* `i *= 2`
* `i /= 2`
* triangular loops
* mixed complexities
* nested loops with dependent bounds

### 3. Practical algorithm analysis

You understand the fundamentals, but we haven't yet applied them extensively to actual DSA problems.

**Do not consider time complexity mastered yet.**

---

# 🧠 Things I Need to Remember

> **Don't look at what the loop does first. Look at how many times it runs.**

And:

```text
Fixed repetitions → O(1)
n repetitions → O(n)
n × n repetitions → O(n²)
```

For space:

```text
Fixed extra memory → O(1)
Memory proportional to n → O(n)
```

---

# 🔁 What Needs Revision

Tomorrow, briefly test:

* `O(1)`
* `O(n)`
* `O(n²)`
* `O(1)` vs `O(n)` space
* Separate vs nested loops

Then move into **`O(log n)`** and begin applying complexity to actual DSA algorithms.

---

# 🚀 Next Recommended Step

**Start with:** `O(log n)`

**First task:** Understand why repeatedly cutting the problem in half produces logarithmic growth.

**Reason:** You've established the basic complexity foundation today; `O(log n)` is the missing fundamental before we start seriously analyzing DSA algorithms.

---

# 📊 Progress Dashboard

### Today's Progress

**DSA**

* Foundations: 🟢
* `O(1)`: 🟢
* `O(n)`: 🟢
* `O(n²)`: 🟢
* Space complexity basics: 🟢
* `O(log n)`: 🔴 Not yet covered

**Problem solving:** 🟡 Early stage — foundational exercises completed.

**LeetCode:** Not recorded today.

**Projects:** None today.

### Overall Progress

**Current phase:** Month 1 — Core DSA Learning
**Current topic:** Time Complexity
**Next:** `O(log n)` → algorithm analysis → Arrays/problem solving

No artificial percentage assigned because we don't yet have enough meaningful data to calculate one.

---

# 📢 Build-in-Public Post

### Day 1 of restarting DSA.

I realized something today:

Knowing that something is `O(n)` isn't enough.

I need to understand **why**.

Today I worked through the foundations of time and space complexity and made a couple of mistakes that actually helped clarify the concept.

The biggest one:

```cpp
for (int i = 0; i < n; i++) {
    cout << arr[0];
}
```

I initially thought this could be `O(1)` because I'm always accessing the same element.

But the operation happens **n times**.

That distinction clicked:

**The cost of one operation ≠ the total number of operations.**

I also learned to distinguish:

`O(n) + O(n) → O(n)`

from

`O(n) × O(n) → O(n²)`

Not trying to rush through DSA this time.

The goal is to reach December 31 being able to look at an unfamiliar problem and actually reason my way through it.

**Day 1 done.**

---

# 💡 Content Ideas

### LinkedIn

**"The Big-O mistake I made on Day 1 of restarting DSA"**

Focus on the `arr[0]` inside an `n` loop.

### Short-form video

**Hook:**
*"I thought this code was O(1). It wasn't."*

Show:

```cpp
for (int i = 0; i < n; i++)
    cout << arr[0];
```

Then explain operation vs repetitions.

### Carousel

**Title:**
**"Stop memorizing Big-O. Learn to count the work."**

Slides:

1. What is `n`?
2. `O(1)`
3. `O(n)`
4. `O(n²)`
5. Separate loops
6. Nested loops
7. Common mistake
8. The mental model

---

# 📝 One-Line Day Summary

**Today I went from basic familiarity with Big-O → to independently reasoning about `O(1)`, `O(n)`, `O(n²)`, and basic space complexity.**

---

### Tomorrow's Starting Point

**Start tomorrow with:** `O(log n)`

**First task:** Explain what happens to the input when it is repeatedly divided in half.

**Reason:** This is the next missing fundamental complexity and will prepare you for algorithms such as binary search.
