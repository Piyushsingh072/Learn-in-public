# 🌙 EOD — DAY 2

**Date:** September 5, 2026
**Phase:** Phase 1 — Core DSA
**Focus:** Time Complexity + Array Fundamentals

## 🎯 Today’s Goal

Build the ability to look at simple DSA code/problems and determine:

* What operation is happening?
* How many times does it happen?
* Time complexity
* Space complexity
* How to solve basic array problems independently

---

# 1. Starting Point

You entered today with the **Big-O foundation already introduced**:

* `O(1)`
* `O(log n)`
* `O(n)`
* `O(n²)`
* Basic time vs space complexity

The goal today was to start **applying complexity analysis to actual DSA problems**, rather than only studying definitions.

---

# 2. 📚 What You Learned

### Time Complexity

You reinforced:

| Complexity | Mental Model                           |
| ---------- | -------------------------------------- |
| `O(1)`     | Constant work                          |
| `O(log n)` | Input repeatedly reduced, e.g. halving |
| `O(n)`     | One pass proportional to input         |
| `O(n²)`    | Nested work proportional to `n × n`    |

### Important distinction reinforced

You initially confused:

> "The operation itself is constant, so the loop must be O(1)."

Example:

```cpp
for(int i = 0; i < n; i++)
    cout << arr[0];
```

`arr[0]` is `O(1)`, **but it happens `n` times**, so the complete loop is:

`O(n)`

This is an important DSA habit:

> **Analyze the total number of operations, not just the individual operation.**

---

# 3. 🧠 Learning Journey

### Concept → Complexity Analysis

You practiced recognizing:

```cpp
cout << arr[0];
```

→ `O(1)`

Then:

```cpp
for(int i = 0; i < n; i++)
    cout << arr[i];
```

→ `O(n)`

Then nested loops:

```cpp
for(int i = 0; i < n; i++)
    for(int j = 0; j < n; j++)
```

→ `O(n²)`

You also reinforced that:

```text
O(n) + O(n) = O(n)
```

and:

```text
O(1) + O(n) + O(n²) = O(n²)
```

---

# 4. 🔍 Space Complexity

You correctly identified:

```cpp
int sum = 0;

for(...)
    sum += arr[i];
```

→ **`O(1)` extra space**

Then:

```cpp
int temp[n];
```

→ **`O(n)` extra space**

You also correctly handled a program containing:

* two `O(n)` loops
* an additional `temp[n]`

Result:

**Time:** `O(n)`
**Space:** `O(n)`

---

# 5. 🧩 Problems Practiced

## Problem 1 — Find Largest

### Result

✅ Correct

You initially used:

```cpp
int maxNum = 0;
```

### Correction

This fails for an array containing only negative numbers.

Better:

```cpp
int maxNum = arr[0];
```

Then compare the remaining elements.

### Key lesson

> Don't assume the input is positive unless the problem explicitly says so.

**Time:** `O(n)`
**Space:** `O(1)`

---

## Problem 2 — Find Minimum

### Result

✅ Correct

You used the same pattern as maximum, reversing the comparison.

**Time:** `O(n)`
**Space:** `O(1)`

---

## Problem 3 — Linear Search

### Result

✅ Correct after correction

Initial issue:

You were printing `"Not Found"` inside the loop whenever an element didn't match.

That can produce:

```text
Not Found
Not Found
Not Found
...
```

even if the target exists later.

### Correction

Use a `found` flag and print the final result **after the search**.

### Key lesson

> Don't decide the final result before examining all relevant input.

**Time:** `O(n)` worst case
**Space:** `O(1)`

---

## Problem 4 — Count Even Numbers

### Result

✅ Correct

You used:

```cpp
if(arr[i] % 2 == 0)
    evenNum++;
```

Correct result: `3`.

**Time:** `O(n)`
**Space:** `O(1)`

---

## Problem 5 — Sum of Array

### Result

✅ Correct

You used the accumulator pattern:

```cpp
sum += arr[i];
```

Correct result:

```text
75
```

**Time:** `O(n)`
**Space:** `O(1)`

Minor style improvement:

```cpp
int sum = 0;
```

is preferable to capitalized `Sum` for a normal variable.

---

## Problem 6 — Count Positive Numbers

### Result

✅ **Independent and correct**

Your code correctly processed:

```cpp
{-3, 5, -1, 8, 0, 2, -7}
```

and produced:

```text
3
```

You also correctly identified:

**Time:** `O(n)`
**Space:** `O(1)`

This is a clean example of the **counting pattern**:

```cpp
if(condition)
    counter++;
```

---

# 6. ❌ Mistake Database

### Mistake 1 — Constant operation vs total loop complexity

**Topic:** Time Complexity

**Initial thought:**
`arr[0]` is constant, therefore the loop is `O(1)`.

**Correct version:**
The operation is `O(1)`, but repeating it `n` times makes the complete algorithm `O(n)`.

**Prevention rule:**

> Always ask: **"How many times does this operation execute?"**

---

### Mistake 2 — Fixed loop vs input-dependent loop

**Topic:** Time Complexity

You initially considered a loop running 10 times as `O(n)`.

Correct:

```cpp
for(int i = 0; i < 10; i++)
```

→ `O(1)`

Even 1,000,000 iterations are still `O(1)` if the number is fixed and independent of `n`.

**Prevention rule:**

> Big-O measures how work **scales with input size**, not whether the program does "a lot" of work.

---

### Mistake 3 — Maximum initialized to zero

**Topic:** Array edge cases

**Initial thought:**

```cpp
int maxNum = 0;
```

**Problem:** Fails for all-negative arrays.

**Correct pattern:**

```cpp
int maxNum = arr[0];
```

**Prevention rule:**

> Test your initialization against negative, zero, and boundary-value inputs.

---

### Mistake 4 — Printing "Not Found" during linear search

**Topic:** Linear Search

**Initial approach:** Print failure for every non-matching element.

**Correction:** Track whether the target was found and print once after the search.

**Prevention rule:**

> A single final conclusion should generally be made **after the search is complete**.

---

# 7. 🟢 Mastery Assessment

| Concept             | Current Level                    | Evidence                               |
| ------------------- | -------------------------------- | -------------------------------------- |
| `O(1)`              | 🟠 Can Implement                 | Correctly analyzed constant operations |
| `O(log n)`          | 🟡 Understood With Guidance → 🟠 | Correctly traced halving loops         |
| `O(n)`              | 🟢 Independent                   | Multiple correct array problems        |
| `O(n²)`             | 🟢 Independent                   | Correctly analyzed nested loops        |
| Space Complexity    | 🟠 Can Implement                 | Correctly classified `O(1)` vs `O(n)`  |
| Array traversal     | 🟢 Independent                   | Multiple successful problems           |
| Counting pattern    | 🟢 Independent                   | Even + positive counting               |
| Linear Search       | 🟠 Can Implement                 | Correct after correction               |
| Edge-case awareness | 🟡                               | Maximum problem exposed weakness       |

**Not claiming mastery yet.** You've demonstrated the fundamentals, but mastery requires repeated independent application and harder variations.

---

# 8. 🔄 Learning Loops

### Completed loops

**Complexity → explanation → attempt → correction → reattempt/understanding**

* Constant vs total loop complexity
* Fixed iterations vs `n` iterations
* Nested loops
* Space complexity

**Problem → attempt → correction → correct implementation**

* Maximum
* Minimum
* Linear search

**Problem → independent implementation**

* Count even numbers
* Sum
* Count positive numbers

### Incomplete loop

**Reverse Array**

You intentionally deferred Problem #7 until tomorrow.

---

# 9. 📊 Problems & Attempts

| Problem                | Result                     | Independent?  |
| ---------------------- | -------------------------- | ------------- |
| Find Largest           | ✅ Correct after correction | 🟡            |
| Find Minimum           | ✅ Correct                  | 🟢            |
| Linear Search          | ✅ Correct after correction | 🟡            |
| Count Even Numbers     | ✅ Correct                  | 🟢            |
| Sum Array              | ✅ Correct                  | 🟢            |
| Count Positive Numbers | ✅ Correct                  | 🟢            |
| Reverse Array          | ⏸️ Deferred                | Not attempted |

**LeetCode today:** Not recorded / not completed in this session.

---

# 10. 💡 Key Insights to Remember

### 1. Operation complexity ≠ algorithm complexity

```cpp
arr[i]
```

may be `O(1)`.

But:

```cpp
for(...)
    arr[i];
```

can be `O(n)`.

---

### 2. Input-dependent growth is what matters

```cpp
for(int i = 0; i < 1000000; i++)
```

is still `O(1)`.

```cpp
for(int i = 0; i < n; i++)
```

is `O(n)`.

---

### 3. Max/min pattern

```cpp
int best = arr[0];

for(int i = 1; i < n; i++) {
    if(arr[i] > best)
        best = arr[i];
}
```

Same structure applies to many future DSA problems.

---

### 4. Counting pattern

```cpp
int count = 0;

for(...) {
    if(condition)
        count++;
}
```

You've now used this pattern for **even numbers and positive numbers**.

---

# 11. 📈 Public Progress Dashboard

### Today

* **DSA:** Array fundamentals + complexity application
* **Concepts practiced:** Time complexity, space complexity, array traversal, counting, search
* **Problems completed:** 6
* **LeetCode:** Not completed/recorded
* **Major mistakes:** 4
* **Current topic:** Arrays
* **Next problem:** Reverse an Array

### Overall Phase 1

* **Current phase:** Core DSA
* **Current DSA topic:** Arrays
* **C++:** Fundamentals + STL completed
* **Projects:** No project work recorded today
* **Recurring weakness:** Edge-case consideration and distinguishing an individual operation from the total algorithm
* **Current strength:** Basic array traversal and simple accumulation/counting problems

No percentage is assigned because we don't have enough evidence to justify a meaningful percentage.

---

# 12. 🧪 Tomorrow's Revision

Before introducing anything new, you'll start with:

### Problem #7 — Reverse an Array

```cpp
int arr[] = {1, 2, 3, 4, 5};
```

Expected:

```text
5 4 3 2 1
```

You'll attempt it **without a hint first**.

Then we'll move forward based on how independently you solve it.

---

# 13. 📢 Build-in-Public Content

### Genuine takeaway from today

A good build-in-public angle is:

> **"I realized that Big-O isn't about how much work a program does — it's about how that work grows with the input."**

The strongest authentic moments were:

* confusing `arr[0]` being `O(1)` with the entire loop being `O(1)`
* learning why a million fixed iterations can still be `O(1)`
* catching the all-negative-array edge case
* solving the final counting problem independently

No achievements beyond what was actually demonstrated are claimed.

---

# 14. 🎯 Tomorrow's Starting Point

**Start tomorrow with:** Problem #7 — Reverse an Array

**First task:** Write the complete solution independently and give time + space complexity.

**Reason:** You've now practiced one-pass array operations extensively. Reversing an array introduces the next important array technique rather than repeating simple counting/summing.

---

### One-line summary

**Today you went from understanding Big-O mostly conceptually → applying `O(1)`, `O(n)`, `O(log n)`, `O(n²)`, and `O(1)/O(n)` space analysis while independently solving basic array problems.**

## Tomorrow's Starting Point

**Start tomorrow with:** Reverse an Array
**First task:** Solve Problem #7 without hints.
**Reason:** Move from simple array traversal/counting into **array manipulation and in-place thinking**.
