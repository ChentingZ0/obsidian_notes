### Insertion Sort
[textbook](https://runestone.academy/ns/books/published/pythonds/SortSearch/TheInsertionSort.html)
Given a sorted list, insert a new-come element. The procedure is to find the exact place where the element should be inserted, and move the following ones. 

The time complexity is $O(1)-O(n)$. The best case is insert a largest one such that no element needs to move, the worst case is insert the smallest one such that all elements needs to move.
![[Pasted image 20230928142433.png]]

If the list is unsorted, what we begin is by assuming that a list with the first element is already sorted. On each pass, insert the current item into the sub list. So there are n-1 elements need to be sorted, the time complexity of the whole procedure is **$O(n^2)$

![insertionsort](https://runestone.academy/ns/books/published/pythonds/_images/insertionsort.png)
```python
def insertionSort(list):
	for index in range(1, len(list))  
	# initial sublist start from the second item
		currentvalue = list[index]
		position = index
		while position > 0 and list[position - 1]>currentvalue:
			list[position] = list[position-1]
			position -= 1
		list[position] = currentvalue

# test
list = [54,26,93,17,77,31,44,55,20]
insertionSort(list)
print(list)
```

