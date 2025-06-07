# 49. Group Anagrams
**Difficulty:** Medium

### 📄 Problem Statement
Given an array of strings strs, group the anagrams together. You can return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

 
### 🧪 Examples
Example 1:
```
Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
```
Example 2:
```
Input: strs = [""]
Output: [[""]]
```
Example 3:
```
Input: strs = ["a"]
Output: [["a"]]
 ```

### ✅ Constraints
- 1 <= strs.length <= 104
- 0 <= strs[i].length <= 100
- strs[i] consists of lowercase English letters.

---

### 💻 Python Code

```python
class Solution(object):
    def groupAnagrams(self, strs):
        d = {}

        if strs == [""]:
            return [strs]
        elif len(strs) == 1:
            return [strs] 

        for i in strs:
            t = ''.join(sorted(i))
            if t in d:
                d[t].append(i)
            else:
                d[t] = [i]

        return d.values()

Time complexity: O(n*m)
Space complexity: O(n)
```
