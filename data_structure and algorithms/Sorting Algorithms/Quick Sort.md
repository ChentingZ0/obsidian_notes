### Quick Sort
Divide and conquer algorithm
Similar to merge sort while not using additional storage. 
The whole procedure could be divided into several steps:

**1. Partition:**
Firstly, select a value called the **pivot value**. Conventionally choose the first item in the list. 
Then do the partition: move the items smaller than the pivot to the left, move the items larger than the pivot to the right. (Define a leftmark and rightmark, move and interchange when should). Return the split point(the correct place where pivot value should locate)

![pivot](https://runestone.academy/ns/books/published/pythonds/_images/firstsplit.png)
![partition](https://runestone.academy/ns/books/published/pythonds/_images/partitionA.png)

```python
def partition(list, first, last):
	pivotvalue = list[first]
	
	leftmark = first + 1
	rightmark = last

	done = False  # boolean variable
	while not done:
		while leftmark <= rightmark and list[leftmark] <= pivotvalue:
			leftmark += 1
		while list[rightmark] >= pivotvalue and rightmark >= leftmark:
			rightmark -= 1
		if rightmark < leftmark:
			done = True
		else:
		# interchange
			temp = list[leftmark]
			list[leftmark] = list[rightmark]
			list[rightmark] = temp
	# done: move the pivot to its correct place(rightmark)
	temp = list[first]
	list[first] = list[rightmark]
	list[rightmark] = temp

	return rightmark

alist = [54,26,93,17,77,31,44,55,20]
quickSort(alist)
print(alist)
```

**2. Quick sort the whole list**
This is done by recursively quick sort the left half and the right half.
![cross](https://runestone.academy/ns/books/published/pythonds/_images/partitionB.png)
```python
def quickSort(list):
	quickSortHelper(list, 0, len(list) - 1)

def quickSortHelper(list, first, last):
	if first < last:
		splitpoint = partition(list, first, last)
		quickSortHelper(list, first, splitpoint-1)
		quickSortHelper(list, splitpoint+1, last)
```

```python
# test
alist = [54,26,93,17,77,31,44,55,20]
quickSort(alist)
print(alist)
```

#### Time Complexity
There is no need for additional memory cost. It happens in-place.
It depends on how we choose the pivot value. 
If the partition always happens always in the middle, there will be be $log(n)$ divisions. In order to find the split point, each of the n items need to be compared with pivot value. Thus the best case take $nlog(n)$.

If the partition always start at the very beginning or the very end, sorting a list of n items divided into sorting 0 and n-1 items, n-1 divided into 0 and n-2 ... each time all items checked. So it takes $O(n^2)$.

A particular technique is to choose median of the three(first, middle, last) as the pivot. It chooses a better "median" value.
