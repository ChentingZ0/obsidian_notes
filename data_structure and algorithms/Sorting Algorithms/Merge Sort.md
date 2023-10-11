### Merge Sort
[textbook](https://runestone.academy/ns/books/published/pythonds/SortSearch/TheMergeSort.html)
Use a divide and conquer strategy
It is a recursive algorithm that continually splits a list in half -> Then sort the two halves -> Merging is the process of taking two smaller sorted lists and combining them together into a single, sorted, new list.
![split](https://runestone.academy/ns/books/published/pythonds/_images/mergesortA.png)
![merge](https://runestone.academy/ns/books/published/pythonds/_images/mergesortB.png)
```python
def mergeSort(list):
	print("Spitting",list)
	if len(list) > 1:
		mid = len(list)//2
		lefthalf = list[:mid]
		righthalf = list[mid:]

		mergeSort(lefthalf)
		mergeSort(righthalf)
# assume lefthalf and righthalf are already sorted
# merge these two together(combine+sorted)
		i,j,k = 0,0,0
		while i<len(lefthalf) and j<len(righthalf):
			if lefthalf[i] <= righthalf[j]:
				list[k] = lefthalf[i]
				i += 1
			else:
				list[k] = righthalf[j]
				j += 1
			k += 1
		# deal with the leftovers
		while i < len(lefthalf):
			list[k] = lefthalf[i]
			i += 1
			k += 1
		while j < len(righthalf):
			list[k] = righthalf[j]
			j += 1
			k += 1
		print("Merging", list)

# test
alist = [54,26,93,17,77,31,44,55,20]
mergeSort(alist)
print(alist)		
```

Here is a more concise way to write "merge two sorted list". The same way as above. (extend function does not have return)
```python
# Another writing way to merge two sorted list
def merge_sorted_lists(list1, list2): 
	merged_list = [] 
	i, j = 0, 0 
	# Merge elements from both lists in sorted order 
	while i < len(list1) and j < len(list2): 
		if list1[i] < list2[j]:
			merged_list.append(list1[i]) 
			i += 1 
		else: 
			merged_list.append(list2[j]) 
			j += 1 
		# Add remaining elements from list1 (if any)
	merged_list.extend(list1[i:]) 
	# Add remaining elements from list2 (if any)
	merged_list.extend(list2[j:]) 
	return merged_list
```

Time complexity analysis:
Firstly, split into halves, we divide a list in half $log(n)$ times
For the merge part,each item will be processed and placed on the sorted list. So the merge operation results in a list of size n requires n operations. Merge sort is an $O(nlog(n))$ algorithm.