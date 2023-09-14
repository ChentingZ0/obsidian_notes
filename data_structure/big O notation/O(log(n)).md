## Binary search
```python
nums = [1,2,3,4,5]
target = 6
l,r = 0, len(nums)-1
while l<=r:
	m = (l+r)//2
	if target < nums[m]:
		r = m - 1
	elif target > nums[m]:
		l = m + 1
	else:
		print(m)
		break

```
$2^{x} = n,   n/2/2/2/2../2$ , it's log(n) complexity 

## Binary search on BST(Binary search Tree)
```python
def search(root, target):
	if not root:
		return False
	if target < root.val:
		return search(root.left, target)
	elif target > root.val:
		return search(root.right, target)
	else:
		return True
```

## Heap push and pop
```python
import heapq
minHeap = []
heap.heappush(minHeap, 5)
heap.heappop(minHeap )
```