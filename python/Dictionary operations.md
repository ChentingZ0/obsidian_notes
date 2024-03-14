How to check if one key is in the dictionary
Just use `in` keyword:
```python
my_dict = {'a': 1, 'b': 2, 'c': 3}
key_to_check = 'b'

if key_to_check in my_dict.keys():
    print("Key exists in the dictionary.")
else:
    print("Key does not exist in the dictionary.")
```
