we mean the worst case wrong time, for example, insert method, we consider insert in the first position, thus all the following elements should move to the next position. That's O(n). If insert in the last element, it will be O(1), similar to append method.
Examples:

```
nums = [1,2,3]
sum(nums)
for i in nums:
	print(n)

nums.insert(1, 100)
nums.remove(100)
print(100 in nums)      # search 

import heapq
heapq.heapify(nums)     # build heap

sliding window problem
```

[Sliding window problem](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
[monotonic stack problem](https://leetcode.com/problems/daily-temperatures/)

