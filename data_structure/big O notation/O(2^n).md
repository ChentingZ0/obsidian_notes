## Recursion
```
def recursion(i, nums):
	if i == len(nums):
		return 0
	branch1 = recursion(i + 1, nums)
	branch2 = recursion(i + 2, nums)
```
