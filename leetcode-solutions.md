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

---

### 📘 [Entry #4/31] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 09:12 PM

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

### 📘 [Entry #5/31] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 09:12 PM

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

### 📘 [Entry #7/31] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 09:12 PM

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

### 📘 [Entry #21/31] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 09:13 PM

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

### 📘 [Entry #27/31] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 09:14 PM

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

### 📘 [Entry #29/31] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 8, 2026, 09:14 PM

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

### 📘 [Entry #2/31] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 9, 2026, 10:36 AM

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

### 📘 [Entry #7/31] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 9, 2026, 10:37 AM

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

### 📘 [Entry #12/31] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 9, 2026, 10:37 AM

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

### 📘 [Entry #13/31] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 9, 2026, 10:37 AM

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

### 📘 [Entry #1/30] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 10, 2026, 07:33 PM

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

### 📘 [Entry #2/30] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 10, 2026, 07:33 PM

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

### 📘 [Entry #14/30] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 10, 2026, 07:34 PM

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

### 📘 [Entry #17/30] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 10, 2026, 07:34 PM

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

### 📘 [Entry #21/30] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 10, 2026, 07:34 PM

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

### 📘 [Entry #23/30] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 10, 2026, 07:34 PM

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

### 📘 [Entry #25/30] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 10, 2026, 07:35 PM

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

### 📘 [Entry #26/30] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 10, 2026, 07:35 PM

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

### 📘 [Entry #1/31] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 07:57 PM

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

### 📘 [Entry #5/31] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 07:57 PM

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

### 📘 [Entry #6/27] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 07:57 PM

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

### 📘 [Entry #17/27] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 07:58 PM

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

### 📘 [Entry #18/27] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 07:58 PM

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

### 📘 [Entry #19/27] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 07:58 PM

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

### 📘 [Entry #25/27] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 07:59 PM

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

### 📘 [Entry #27/27] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 07:59 PM

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

### 📘 [Entry #5/30] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 08:59 PM

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

### 📘 [Entry #9/30] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 09:00 PM

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

### 📘 [Entry #10/30] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 09:00 PM

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

### 📘 [Entry #19/30] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 11, 2026, 09:01 PM

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

### 📘 [Entry #4/28] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:35 PM

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

### 📘 [Entry #7/28] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:35 PM

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

### 📘 [Entry #9/28] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:35 PM

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

### 📘 [Entry #19/28] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:36 PM

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

### 📘 [Entry #20/28] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:36 PM

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

### 📘 [Entry #21/28] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:36 PM

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

### 📘 [Entry #23/28] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:36 PM

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

### 📘 [Entry #24/28] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:36 PM

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

### 📘 [Entry #25/28] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:36 PM

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

### 📘 [Entry #28/28] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 12, 2026, 08:37 PM

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

### 📘 [Entry #10/28] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 13, 2026, 08:47 PM

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

### 📘 [Entry #12/28] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 13, 2026, 08:48 PM

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

### 📘 [Entry #13/28] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 13, 2026, 08:48 PM

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

### 📘 [Entry #14/28] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 13, 2026, 08:48 PM

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

### 📘 [Entry #7/28] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 13, 2026, 08:52 PM

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

### 📘 [Entry #8/28] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 13, 2026, 08:52 PM

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

### 📘 [Entry #9/28] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 13, 2026, 08:52 PM

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

### 📘 [Entry #15/28] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 13, 2026, 08:53 PM

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

### 📘 [Entry #20/28] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 13, 2026, 08:53 PM

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

### 📘 [Entry #1/35] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 14, 2026, 09:51 PM

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

### 📘 [Entry #5/35] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 14, 2026, 09:51 PM

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

### 📘 [Entry #12/35] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 14, 2026, 09:52 PM

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

### 📘 [Entry #17/35] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 14, 2026, 09:52 PM

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

### 📘 [Entry #22/35] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 14, 2026, 09:53 PM

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

### 📘 [Entry #25/35] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 14, 2026, 09:53 PM

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

### 📘 [Entry #31/35] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 14, 2026, 09:53 PM

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

### 📘 [Entry #32/35] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 14, 2026, 09:53 PM

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

### 📘 [Entry #34/35] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 14, 2026, 09:54 PM

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

### 📘 [Entry #2/36] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 15, 2026, 09:23 PM

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

### 📘 [Entry #3/36] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 15, 2026, 09:23 PM

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

### 📘 [Entry #8/36] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 15, 2026, 09:24 PM

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

### 📘 [Entry #17/36] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 15, 2026, 09:24 PM

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

### 📘 [Entry #23/36] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 15, 2026, 09:25 PM

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

### 📘 [Entry #24/36] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 15, 2026, 09:25 PM

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

### 📘 [Entry #26/36] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 15, 2026, 09:25 PM

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

### 📘 [Entry #31/36] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 15, 2026, 09:25 PM

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

### 📘 [Entry #3/26] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 16, 2026, 09:20 PM

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

### 📘 [Entry #7/26] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 16, 2026, 09:20 PM

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

### 📘 [Entry #15/26] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 16, 2026, 09:21 PM

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

### 📘 [Entry #17/26] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 16, 2026, 09:21 PM

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

### 📘 [Entry #23/26] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 16, 2026, 09:21 PM

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

### 📘 [Entry #2/35] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 17, 2026, 09:24 PM

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

### 📘 [Entry #3/35] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 17, 2026, 09:24 PM

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

### 📘 [Entry #6/35] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 17, 2026, 09:25 PM

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

### 📘 [Entry #16/35] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 17, 2026, 09:25 PM

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

### 📘 [Entry #23/35] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 17, 2026, 09:26 PM

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

### 📘 [Entry #28/35] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 17, 2026, 09:26 PM

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

### 📘 [Entry #4/34] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 18, 2026, 08:56 PM

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

### 📘 [Entry #7/34] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 18, 2026, 08:56 PM

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

### 📘 [Entry #13/34] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 18, 2026, 08:56 PM

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

### 📘 [Entry #16/34] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 18, 2026, 08:57 PM

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

### 📘 [Entry #20/34] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 18, 2026, 08:57 PM

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

### 📘 [Entry #23/34] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 18, 2026, 08:57 PM

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

### 📘 [Entry #25/34] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 18, 2026, 08:57 PM

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

### 📘 [Entry #27/34] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 18, 2026, 08:57 PM

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

### 📘 [Entry #33/34] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 18, 2026, 08:58 PM

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

### 📘 [Entry #8/31] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 19, 2026, 08:43 PM

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

### 📘 [Entry #12/31] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 19, 2026, 08:44 PM

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

### 📘 [Entry #13/31] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 19, 2026, 08:44 PM

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

### 📘 [Entry #19/31] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 19, 2026, 08:44 PM

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

### 📘 [Entry #21/31] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 19, 2026, 08:44 PM

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

### 📘 [Entry #22/31] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 19, 2026, 08:44 PM

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

### 📘 [Entry #23/31] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 19, 2026, 08:44 PM

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

### 📘 [Entry #25/31] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 19, 2026, 08:45 PM

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

### 📘 [Entry #3/32] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 20, 2026, 08:51 PM

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

### 📘 [Entry #9/32] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 20, 2026, 08:51 PM

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

### 📘 [Entry #13/32] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 20, 2026, 08:52 PM

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

### 📘 [Entry #19/32] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 20, 2026, 08:52 PM

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

### 📘 [Entry #20/32] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 20, 2026, 08:52 PM

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

### 📘 [Entry #25/32] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 20, 2026, 08:53 PM

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

### 📘 [Entry #32/32] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 20, 2026, 08:53 PM

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

### 📘 [Entry #3/34] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 21, 2026, 10:00 PM

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

### 📘 [Entry #10/34] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 21, 2026, 10:00 PM

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

### 📘 [Entry #15/34] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 21, 2026, 10:01 PM

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

### 📘 [Entry #17/34] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 21, 2026, 10:01 PM

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

### 📘 [Entry #23/34] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 21, 2026, 10:01 PM

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

### 📘 [Entry #29/34] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 21, 2026, 10:02 PM

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

### 📘 [Entry #1/36] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 22, 2026, 09:21 PM

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

### 📘 [Entry #3/36] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 22, 2026, 09:21 PM

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

### 📘 [Entry #4/36] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 22, 2026, 09:21 PM

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

### 📘 [Entry #19/36] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 22, 2026, 09:23 PM

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

### 📘 [Entry #25/36] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 22, 2026, 09:23 PM

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

### 📘 [Entry #27/36] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 22, 2026, 09:23 PM

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

### 📘 [Entry #32/36] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 22, 2026, 09:24 PM

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

### 📘 [Entry #34/36] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 22, 2026, 09:24 PM

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

### 📘 [Entry #36/36] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 22, 2026, 09:24 PM

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

### 📘 [Entry #4/33] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 23, 2026, 09:32 PM

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

### 📘 [Entry #10/33] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 23, 2026, 09:32 PM

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

### 📘 [Entry #18/33] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 23, 2026, 09:33 PM

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

### 📘 [Entry #19/33] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 23, 2026, 09:33 PM

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

### 📘 [Entry #23/33] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 23, 2026, 09:33 PM

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

### 📘 [Entry #25/33] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 23, 2026, 09:33 PM

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

### 📘 [Entry #1/32] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 24, 2026, 09:32 PM

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

### 📘 [Entry #2/32] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 24, 2026, 09:32 PM

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

### 📘 [Entry #18/32] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 24, 2026, 09:34 PM

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

### 📘 [Entry #19/32] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 24, 2026, 09:34 PM

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

### 📘 [Entry #24/32] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 24, 2026, 09:34 PM

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

### 📘 [Entry #25/32] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 24, 2026, 09:34 PM

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

### 📘 [Entry #2/28] LeetCode #20: Valid Parentheses (Stack Pattern)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 25, 2026, 09:37 PM

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

### 📘 [Entry #11/28] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 25, 2026, 09:38 PM

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

### 📘 [Entry #14/28] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 25, 2026, 09:38 PM

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

### 📘 [Entry #16/28] LeetCode #1: Two Sum (Optimal Hash Map Approach)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 25, 2026, 09:38 PM

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

### 📘 [Entry #20/28] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 25, 2026, 09:38 PM

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

### 📘 [Entry #25/28] LeetCode #206: Reverse Linked List (Iterative & Recursive)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 25, 2026, 09:39 PM

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

### 📘 [Entry #28/28] LeetCode #53: Maximum Subarray (Kadane's Algorithm)
> **Track:** `LEETCODE-SOLUTIONS` | **Updated:** Sep 25, 2026, 09:39 PM

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
