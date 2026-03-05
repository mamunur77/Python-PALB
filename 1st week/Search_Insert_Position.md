# Search Insert Position

Given a **sorted array of distinct integers** and a **target value**, return the **index if the target is found**. If not, return the **index where it would be if it were inserted in order**.

You must write an algorithm with **O(log n)** runtime complexity.

---

## Examples

**Input:**  
nums = [1,3,5,6], target = 5  

**Output:**  
2  

---

**Input:**  
nums = [1,3,5,6], target = 2  

**Output:**  
1  

---

**Input:**  
nums = [1,3,5,6], target = 7  

**Output:**  
4  

---

## Constraints

1 ≤ nums.length ≤ 10⁴  
-10⁴ ≤ nums[i] ≤ 10⁴  
nums contains **distinct values sorted in ascending order**.  
-10⁴ ≤ target ≤ 10⁴  

---

## Solution

```python
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        left = 0
        right = len(nums) - 1
        
        while left <= right:
            mid = (left + right) // 2
            
            if nums[mid] == target:
                return mid
            elif nums[mid] < target:
                left = mid + 1
            else:
                right = mid - 1
        
        return left
```

## Problem Solved Screenshot

![Problem Solved Screenshot](image8.png)
