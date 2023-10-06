### Subsets
[leetcode](https://leetcode.com/problems/subsets/description/)
Decision tree:
for every element, either choose or not choose

![[Pasted image 20231006215434.png]]

Still hold the general pattern
```python
class Solution:
	def subsets(self, nums: List[int]) -> List[List[int]]:
		res = []
		subset = []
	
		def dfs(index):
			if index >= len(nums):
				res.append(subset.copy())
				return ## Goal, base case, when to stop the recursion
			subset.append(nums[index]) # Choice
			dfs(index+1)
			subset.pop() # undo the choice(back to the previous point)
			dfs(index+1) ## Choices and recursion. No constrain in this problem
		dfs(0)
		return res
```


### 