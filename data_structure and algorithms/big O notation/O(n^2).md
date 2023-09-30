Nested loop:
```python
# Traverse a square grid
nums = [[1,2,3], [4,5,6], [7,8,9]]
for i in range(len(nums)):
	for j in range(len(nums[i])):
		print(nums[i][j])

# 
nums = [1,2,3]
for i in range(len(nums)):
	for j in range(i+1, len(nums)):
		print(nums[i], nums[j])

O(n^2/2) --> O(n^2)
```

