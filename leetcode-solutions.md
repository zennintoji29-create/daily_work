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

---

### 📘 [Entry #11/31] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Reversing pointers in a singly linked list in-place using `prev`, `curr`, and `next` pointers.

#### 💻 Code & Implementation
```java
// LeetCode #206: Reverse Linked List
class ListNode {
    int val;
    ListNode next;
    ListNode(int val) { this.val = val; }
}

class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode curr = head;

        while (curr != null) {
            ListNode nextTemp = curr.next; // 1. Save next node
            curr.next = prev;              // 2. Reverse pointer to point backwards
            prev = curr;                   // 3. Advance prev pointer
            curr = nextTemp;               // 4. Advance curr pointer
        }

        return prev; // prev is the new head of reversed list
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Always store `curr.next` before overwriting it; otherwise, the rest of the list is lost.
- In-place pointer reversal operates without creating any new node allocations.
- **Complexity**: Time: O(N) | Space: O(1) in-place.

---

### 📘 [Entry #19/31] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Validating balanced brackets `()`, `{}`, `[]` using a LIFO Stack data structure.

#### 💻 Code & Implementation
```java
// LeetCode #20: Valid Parentheses
import java.util.Stack;

class Solution {
    public boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();

        for (char c : s.toCharArray()) {
            // Push expected closing bracket onto stack
            if (c == '(') stack.push(')');
            else if (c == '{') stack.push('}');
            else if (c == '[') stack.push(']');
            else {
                // If stack is empty or doesn't match current closing bracket
                if (stack.isEmpty() || stack.pop() != c) {
                    return false;
                }
            }
        }

        // Valid only if all opened brackets were closed
        return stack.isEmpty();
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Pushing the *matching closing character* makes the check a simple single equality comparison `stack.pop() != c`.
- LIFO (Last In First Out) naturally matches nested matching structures like HTML tags and mathematical parentheses.
- **Complexity**: Time: O(N) | Space: O(N) stack size.

---

### 📘 [Entry #22/31] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 7, 2026, 10:16 PM

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

### 📘 [Entry #28/31] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 7, 2026, 10:16 PM

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

### 📘 [Entry #3/35] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 10:26 AM

#### 💡 Overview
Validating balanced brackets `()`, `{}`, `[]` using a LIFO Stack data structure.

#### 💻 Code & Implementation
```java
// LeetCode #20: Valid Parentheses
import java.util.Stack;

class Solution {
    public boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();

        for (char c : s.toCharArray()) {
            // Push expected closing bracket onto stack
            if (c == '(') stack.push(')');
            else if (c == '{') stack.push('}');
            else if (c == '[') stack.push(']');
            else {
                // If stack is empty or doesn't match current closing bracket
                if (stack.isEmpty() || stack.pop() != c) {
                    return false;
                }
            }
        }

        // Valid only if all opened brackets were closed
        return stack.isEmpty();
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Pushing the *matching closing character* makes the check a simple single equality comparison `stack.pop() != c`.
- LIFO (Last In First Out) naturally matches nested matching structures like HTML tags and mathematical parentheses.
- **Complexity**: Time: O(N) | Space: O(N) stack size.

---

### 📘 [Entry #8/35] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 10:26 AM

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

---

### 📘 [Entry #10/35] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 10:26 AM

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

### 📘 [Entry #16/35] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 10:27 AM

#### 💡 Overview
Reversing pointers in a singly linked list in-place using `prev`, `curr`, and `next` pointers.

#### 💻 Code & Implementation
```java
// LeetCode #206: Reverse Linked List
class ListNode {
    int val;
    ListNode next;
    ListNode(int val) { this.val = val; }
}

class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode curr = head;

        while (curr != null) {
            ListNode nextTemp = curr.next; // 1. Save next node
            curr.next = prev;              // 2. Reverse pointer to point backwards
            prev = curr;                   // 3. Advance prev pointer
            curr = nextTemp;               // 4. Advance curr pointer
        }

        return prev; // prev is the new head of reversed list
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Always store `curr.next` before overwriting it; otherwise, the rest of the list is lost.
- In-place pointer reversal operates without creating any new node allocations.
- **Complexity**: Time: O(N) | Space: O(1) in-place.

---

### 📘 [Entry #34/35] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 10:28 AM

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

---

### 📘 [Entry #2/31] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 09:12 PM

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
