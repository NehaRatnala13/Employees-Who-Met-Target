# 2798. Employees Who Met Target

**Difficulty:** Easy  
**Topics:** Array  
**Problem Link:** [LeetCode 2798](https://leetcode.com/problems/number-of-employees-who-met-the-target/)

---

## Problem Description

A company employs `n` workers indexed `0` through `n - 1`. An integer array `hours` records how long each worker spent on the job. Management expects a minimum of `target` hours from everyone.

Given `hours` (length `n`, non-negative integers) and `target` (non-negative integer), return how many workers logged at least `target` hours.

---

## Examples

### Example 1
* **Input:** `hours = [0, 1, 2, 3, 4]`, `target = 2`
* **Output:** `3`
* **Why:** Workers 2, 3, and 4 logged 2, 3, and 4 hours, meeting the 2-hour minimum; workers 0 and 1 fell short.

### Example 2
* **Input:** `hours = [5, 1, 4, 2, 2]`, `target = 6`
* **Output:** `0`
* **Why:** Nobody reached the 6-hour threshold.

---

## Constraints

* `1 <= n == hours.length <= 50`
* `0 <= hours[i], target <= 10^5`

---

## Approach

Scan the `hours` array once from start to finish. Maintain a counter initialized to `0`, and add `1` whenever an entry is greater than or equal to `target`.

* **Time Complexity:** O(n) — each worker's hours are checked once.
* **Space Complexity:** O(1) — only a single counter variable is needed.

---

## Solutions

### Python
```python
class Solution:
    def countMetTarget(self, worked: list[int], goal: int) -> int:
        return sum(1 for h in worked if h >= goal)
```

