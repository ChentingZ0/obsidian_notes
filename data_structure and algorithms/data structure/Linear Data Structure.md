Stack, Queue, Deque
#### Stack data structure
last-in first-out
![example](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e4/Lifo_stack.svg/1280px-Lifo_stack.svg.png)
`push(item)`: adds to the top
`pop()`: removes the top item from the stack
`peek()` : returns the top item but not remove it
`isEmpty()`: test if empty, return boolean value
`size`: return number of items on the stack, return an integer

In python default:
```python
stack = []
stack.append(...)
element = stack.pop()
```

#### Queue data structure
first-in first-out
can access both ends
![queue](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20221213113312/Queue-Data-Structures.png)

#### Deque(namely double ended queue)
double-ended queue. New items can be added at either the front or the rear. Likewise, existing items can be removed from either end.
`addFront(item)`, `addRear(item)`,`removeFront()`,`removeRear()`
![deque](https://media.geeksforgeeks.org/wp-content/uploads/anod.png)

`popleft()`, `popright()`
```python
# queue
q = collections.deque()
q.append(...)
q.popleft(...)

# set
visit = set()
visit.add(...)
```
