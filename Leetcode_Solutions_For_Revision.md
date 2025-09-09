```markdown
# 🚀 LeetCode Solutions in Java  

Welcome to my **colorful & fun revision notes** 🎨  
This document stores all my **LeetCode problem solutions** (Java) with clear **Approach 🧠** and **Intuition 💡**.  

Format followed for every problem:  
👉 **Question → Solution(s) → Approach → Intuition**

---

## 🔢 485. Max Consecutive Ones  

### 📌 Question  
Given a binary array nums, return the maximum number of consecutive 1's in the array.  

**Example 1:**  
Input: `[1,1,0,1,1,1]`  
Output: `3`  
Explanation: The first two digits or the last three digits are consecutive 1s. The maximum number of consecutive 1s is 3.  

**Example 2:**  
Input: `[1,0,1,1,0,1]`  
Output: `2`  

**Constraints:**  
- 1 <= nums.length <= 100000  
- nums[i] is either 0 or 1  

---

### ✅ Solution (Optimal - O(n) Time, O(1) Space)

```java
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int currentStreak = 0;   // current consecutive 1s
        int maxStreak = 0;       // longest streak seen so far

        for (int num : nums) {
            if (num == 1) {
                currentStreak++;
            } else {
                maxStreak = Math.max(maxStreak, currentStreak);
                currentStreak = 0;
            }
        }
        return Math.max(maxStreak, currentStreak);
    }
}

```

----------

### 🧠 Approach

-   Traverse the array once.
    
-   Maintain two counters:
    
    -   **currentStreak** → current sequence of 1s.
        
    -   **maxStreak** → longest streak so far.
        
-   On `1` → increment `currentStreak`.
    
-   On `0` → update `maxStreak` and reset `currentStreak`.
    
-   Answer = max of both at the end.
    

⏱ **Time Complexity:** O(n)  
💾 **Space Complexity:** O(1)

----------

### 💡 Intuition

We want the longest continuous run of 1s.  
By **tracking the current streak** and **comparing when streak breaks**, we always keep the longest.  
Efficient one-pass solution, no extra memory needed 🚀

----------