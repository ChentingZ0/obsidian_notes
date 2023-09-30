Compare adjacent items and exchange those that are out of order. Each item bubbles up to the location where it belongs
![bubble](https://runestone.academy/ns/books/published/pythonds/_images/bubblepass.png)
At each pass, one item bubbles to its right place(93 in this case). Next pass, n-1 items need to compare.

```python
def BubbleSort(list):
	exchanges = True
	passnum = len(list) - 1
	while passnum > 0 and exchanges == True:
		exchanges = False
		for i in range(passnum):
			if list[i] > list[i+1]:
				exchanges = True
				temp = list[i]
				list[i] = list[i+1]
				list[i+1] = temp
		passnum = passnum - 1

alist=[20,30,40,90,50,60,70,80,100,110]
shortBubbleSort(alist)
print(alist)
```

#### Time complexity analysis
The best case: already sorted, in every comparison, no swap whatsoever. the number of comparisons required is n-1 and the number of swaps required = 0. Hence the best case complexity is $O(n)$.

The worst case: every comparison will cause an exchange(in a decreasing order)
At pass 1:  
Number of comparisons = (N-1)  
Number of swaps = (N-1)

At pass 2:  
Number of comparisons = (N-2)  
Number of swaps = (N-2)

At pass 3:  
Number of comparisons = (N-3)  
Number of swaps = (N-3)  

At pass N-1:  
Number of comparisons = 1  
Number of swaps = 1

Now, calculating total number of comparison required to sort the array  
= (N-1) + (N-2) +  (N-3) + . . . 2 + 1  
= (N * (N-1)) / 2

In worst case, Total number of swaps = Total number of comparison.
Total number of comparison (Worst case) = N(N-1)/2 
Total number of swaps (Worst case) = N(N-1)/2

So worst case time complexity is $O(n^2)$ 