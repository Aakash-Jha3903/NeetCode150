# 347. Top K Frequent Elements
**Difficulty:**  Medium

### 📄 Problem Statement
Given an integer array nums and an integer k, return the k most frequent elements. You may return the answer in any order.


### 🧪 Examples
Example 1:
```
Input: nums = [1,1,1,2,2,3], k = 2
Output: [1,2]
```
Example 2:
```
Input: nums = [1], k = 1
Output: [1]
 ```

### ✅ Constraints

- 1 <= nums.length <= 105
- k is in the range [1, the number of unique elements in the array].
- It is guaranteed that the answer is unique.
 

### Follow up: Your algorithm's time complexity must be better than O(n log n), where n is the array's size.

---

### 💻 Python Code

```python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        count = {}
        for num in nums:
            count[num] = 1 + count.get(num, 0)

        heap = []
        for num in count.keys():
            heapq.heappush(heap, (count[num], num))
            if len(heap) > k:
                heapq.heappop(heap)

        res = []
        for i in range(k):
            res.append(heapq.heappop(heap)[1])
        return res

Time complexity: O(nlogk)
Space complexity: O(n+k)
```
