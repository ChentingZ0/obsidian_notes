- 创建np.zeros多维的方法，把维度信息放在一个tuple,再代入
```python
dimensions = (self.n_states,self.n_states,self.n_actions)  
transition_probabilities = np.zeros(dimensions)
```

- `.get('T', 20)` 函数，针对字典的函数
```python
T = kwargs.get('T', 20)
```
在 Python 中，表达式 `T = kwargs.get('T', 20)` 是一种从一个名为 `kwargs` 的字典中获取与键 `'T'` 相关联的值的方法。如果字典 `kwargs` 中存在键 `'T'`，则 `T` 将被赋予与该键关联的值；如果不存在，`T` 将被赋予默认值 `20`。

1. **`kwargs`**: 这通常是一个函数参数，表示 "keyword arguments"（关键字参数）。它是一个字典，其中包含了函数调用时传递的所有关键字参数。
    
2. **`.get()` 方法**: 这是 Python 字典类型的一个方法。它接受两个参数：要检索的键和一个默认值。如果字典中存在指定的键，则 `.get()` 返回该键的值。如果不存在，则返回默认值。

- `it = iter(iterable)`

- `zip(.., ..)`

`A**(n)` for exponentiation


`time.sleep`