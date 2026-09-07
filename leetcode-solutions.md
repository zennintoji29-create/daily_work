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

---

### 📘 [Entry #10/31] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Find two numbers in an array that add up to a target sum using single-pass Hash Map.

#### 💻 Code & Implementation
```java
// LeetCode #1: Two Sum
// Given an array of integers nums and an integer target, return indices of the two numbers.
import java.util.HashMap;
import java.util.Map;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        // Map to store: number -> its index
        Map<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            
            // If complement exists in map, we found the pair!
            if (map.containsKey(complement)) {
                return new int[] { map.get(complement), i };
            }
            
            // Store current number and its index
            map.put(nums[i], i);
        }

        return new int[] {}; // No solution found
    }
}
```

#### 🎯 Key Concepts & Takeaways
- **Brute Force**: Check every pair with nested loops: O(N^2) Time.
- **Optimal HashMap**: Calculate `complement = target - current`. If complement was previously seen in the map, return both indices immediately in O(1) lookup time.
- **Complexity**: Time: O(N) single pass | Space: O(N) hash map storage.
