# 💡 LeetCode Problem Solutions & Intuition

> Solved LeetCode patterns with problem breakdown, optimal algorithms, and complexity analysis.


---

### 📘 [Entry #2/31] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 7, 2026, 10:14 PM

#### 💡 Overview
Finding contiguous subarray with the largest sum using dynamic programming in linear time.

#### 💻 Code & Implementation
```java
// LeetCode #53: Maximum Subarray
class Solution {
    public int maxSubArray(int[] nums) {
        int currentMax = nums[0];
        int globalMax = nums[0];

        for (int i = 1; i < nums.length; i++) {
            // Either extend the existing subarray or start a fresh subarray at nums[i]
            currentMax = Math.max(nums[i], currentMax + nums[i]);
            // Update the overall highest sum seen so far
            globalMax = Math.max(globalMax, currentMax);
        }

        return globalMax;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- **Kadane's Intuition**: If the running sum becomes negative, it can never contribute positively to any future subarray, so we reset the subarray at the current element.
- **Complexity**: Time: O(N) single pass | Space: O(1) constant memory.
