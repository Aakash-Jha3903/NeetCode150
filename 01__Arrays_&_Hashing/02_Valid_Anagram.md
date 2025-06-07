# 242. Valid Anagram
**Difficulty:** Easy

### 📄 Problem Statement
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

 
### 🧪 Examples
Example 1:
```
Input: s = "anagram", t = "nagaram"
Output: true
```
Example 2:
```
Input: s = "rat", t = "car"
Output: false
 ```

### ✅ Constraints

- 1 <= s.length, t.length <= 5 * 104
- s and t consist of lowercase English letters.

Follow up: What if the inputs contain Unicode characters? How would you adapt your solution to such a case?
 

### 💻 Python Code

```python

# 1) Method : Sorting
class Solution(object):
    def isAnagram(self, s, t):
        if len(s) != len(t):
            return False
        return sorted(s) == sorted(t) # comparing LISTs.... 

Time complexity: O(nlogn + mlogm)
Space complexity: O(1) or O(n + m) depends on sorting algo.


# 2) Method : Hash Map
class Solution(object):
    def isAnagram(self, s, t):
        if len(s) != len(t):
            return False

        countS, countT = {}, {}
        for i in range(len(s)):
            countS[s[i]] = 1 + countS.get(s[i], 0)
            countT[t[i]] = 1 + countT.get(t[i], 0)
        return countS == countT

Time complexity: O(n + m)
Space complexity: O(1) as we have max 26 different characters.