`rstrip()`:
```python
text = "banana,,,,,ssqqqww....."
result = text.rstrip(',.qw')
print(result)
```

------------------------------------

`s: str`
`count = s.count('1')`
返回string s中数字1出现的次数

-------------------------------------
```python
s = "dog cat cat dog"
words = s.split(' ') # 根据空格提取s中的单词
```
The words variable will be a list that contains the following strings: `['dog', 'cat', 'cat', 'dog']`

----------------------
- Reverse a string
```python
my_string = "Hello, World!"
reversed_string = my_string[::-1]
print(reversed_string)
```

- Concatenate two strings
```python
string1 = "Hello, "
string2 = "World!"
combined_string = string1 + string2
print(combined_string)
```

- Join elements in a list into a string
```python
stack = [xx, xx, xx]
res = '/'.join(stack)
```
