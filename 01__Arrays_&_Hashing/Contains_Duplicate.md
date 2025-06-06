# 217. Contains Duplicate
**Difficulty:** Easy

### 📄 Problem Statement
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

 
### 🧪 Examples
Example 1:
```
Input: nums = [1,2,3,1]
Output: true
```
Example 2:
```
Input: nums = [1,2,3,4]
Output: false
```
Example 3:
```
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true
 ```

### ✅ Constraints

- 1 <= nums.length <= 105
- -109 <= nums[i] <= 109

### 💡 Approach
Use a set to keep track of seen numbers.  
If a number is already in the set, return `True` immediately.  
If the loop completes, return `False`.

---

### 💻 Python Code

```python

# 1) Method : Hash Set
class Solution:
    def containsDuplicate(self, nums):
        seen = set()
        for num in nums:
            if num in seen:
                return True
            seen.add(num)
        return False

Time complexity: O(n)
Space complexity: O(n)



# 2) Method : Hash Set Length
class Solution:
    def containsDuplicate(self, nums):
    return len(set(nums)) < len(nums)
    
Time complexity: O(n)
Space complexity: O(n)
