priority queue is a useful data structure for some of the [[graph algorithms]]

Classic way to implement a priority queue is using Binary heap.

[Youtube video](https://www.youtube.com/watch?v=HqPJF2L5h9U&ab_channel=AbdulBari)
Firstly -> binary tree -> full/complete binary tree
## Heap: 堆 
Heap is a complete binary tree!
#### Min heap
(smallest key always the front)
Every parent is having the value smaller  than its descendants.
#### Max heap
(largest key always the front)
Every parent is having the value greater than its descendants.
#### Delete
Only delete the top one apple
direction: from top to bottom
O(log(n))
#### Insert
compare with the ancestors on that particular route. Depend on the height of the binary tree.  O(log(n))
direction: from bottom to top
#### Sort
Firstly: heap creation:
Insert n elements, each one O(log(n)), overall O(n*log(n))

Delete the element and fill in the empty space
automatically getting sorted 
Deleting n elements: O(nlog(n))
Overall: O(2nlog(n)) = O(nlog(n))

#### Heapify
For heapify, direction is different
starting from the last element
O(n)

#### priority queues
Heap is the faster data structure for priority queue.
For smaller number priority, use min heap
For large number priority, use max heap