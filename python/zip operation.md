zip(*batch)" suggests that you want to restructure this batch of data. 
The `zip` function in Python is used to combine several iterables (like lists, tuples, etc.) element-wise. The `*` operator, when used with `zip` and an iterable of iterables (like the one shown), unpacks each iterable and passes them as separate arguments to `zip`.

```python
batch = [(array_1, int_1, bool_1), (array_2, int_2, bool_2), ...]
```

Applying `zip(*batch)` would reorganize this structure into something like this:

```python
zipped = [(array_1, array_2, ...), (int_1, int_2, ...), (bool_1, bool_2, ...)]
```

- **Tutorial**
```python
iterable1 = [1, 2, 3]
iterable2 = ['a', 'b', 'c']

zipped = zip(iterable1, iterable2)
for pair in zipped:
    print(pair)

output:
(1, 'a')
(2, 'b')
(3, 'c')
```

*Upzip:*
```python
pairs = [(1, 'a'), (2, 'b'), (3, 'c')]
numbers, letters = zip(*pairs)

output:
numbers = (1, 2, 3)
letters = ('a', 'b', 'c')
```

- **Iteration**
Given two strings, iterate through characters in them simutaneously
It can also be different data structure zipped together
```python
s: str, t: str
for char1, char2 in zip(s, t):
	...
=

for i in range(len(s)):
	char1 = s[i]
	char2 = t[i]
```
